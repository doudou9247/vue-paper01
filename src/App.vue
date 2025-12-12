<template>
  <Background />
  <div class="page">
    <Title />
  </div>
  <div class="speaker-switch">
    <SpeakerSwitch />
  </div>
</template>

<script setup>
import Background from '@/components/Background.vue'
import Title from '@/components/Title.vue'
import SpeakerSwitch from './components/SpeakerSwitch.vue'



</script>

<style>
.page {
  position: relative;
  z-index: 1;
  color: white;
  padding: 100px;
}

</style>