<template>
  <div class="bg-container" :style="bgStyle">
    <slot />
  </div>
</template>

<script setup>
import bg from '@/assets/bg.png'

const bgStyle = {
  backgroundImage: `url(${bg})`,
  backgroundSize: 'contain',
  backgroundPosition: 'center center',
  backgroundRepeat: 'no-repeat',
}
</script>

<style scoped>
.bg-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: -1;
}
</style>