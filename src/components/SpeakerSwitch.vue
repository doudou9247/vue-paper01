<template>
  <div
      @click="toggleSpeaker"
      style="
      cursor: pointer;
      position: fixed;
      top: 10px;
      left: 100px;
      z-index: 1000;
      transform: scale(1.2);
      transition: opacity 0.3s ease;
      "
  >
    <img
        src="@/assets/1.png"
        alt="喇叭"
        :style="{
          width: '80px',
          height: '80px',
          opacity: isPlaying ? 1 : 0.5
        }"
    />
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import musicSrc from '@/assets/1.mp3'

const isPlaying = ref(false)


const audio = new Audio(musicSrc)
audio.loop = true


const toggleSpeaker = () => {
  if (isPlaying.value) {
    audio.pause()
  } else {
    audio.play().catch(e => {
      console.error("播放失败:", e);

      isPlaying.value = false;
    })
  }
  isPlaying.value = !isPlaying.value
}


onMounted(() => {
  audio.pause()
  isPlaying.value = false
})

onBeforeUnmount(() => {
  audio.pause()
})
</script>
