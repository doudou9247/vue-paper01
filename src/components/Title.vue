<template>
  <div class="school-title-container">
    <div class="title-word title-green">校</div>
    <div class="title-word title-green">园</div>
    <div class="title-word title-blue">安</div>
    <div class="title-word title-blue">全</div>
    <div class="title-word title-red">我</div>
    <div class="title-word title-red">知</div>
    <div class="title-word title-red">道</div>
  </div>
</template>

<script setup>
</script>

<style scoped lang="scss">
@use "sass:color";

// 颜色定义
$color-green: #388e8e;
$color-blue: #1976d2;
$color-red: #d32f2f;
$base-white: #ffffff;
$outline-color: rgba(0, 0, 0, 0.1);

// --- 容器样式 ---
.school-title-container {
  position: fixed;
  top: 20px;
  right: 380px;

  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;

  transform: scale(0.8);
  transform-origin: top right;
  z-index: 1000;
}


// --- 单字样式 ---
.title-word {
  font-size: 80px;
  font-weight: bold;
  line-height: 1;
  padding: 15px 20px;
  background-color: $base-white;
  border-radius: 20px;

  box-shadow:
      0 4px 0 $outline-color,
      0 0 0 5px $base-white,
      -3px -3px 0 0 rgba(0, 0, 0, 0.15) inset;

  &:nth-child(even) {
    transform: rotate(1deg) translateY(-2px);
  }
  &:nth-child(odd) {
    transform: rotate(-1deg) translateY(2px);
  }

  text-shadow:
      -2px -2px 0 $base-white,
      2px -2px 0 $base-white,
      -2px 2px 0 $base-white,
      2px 2px 0 $base-white,
      4px 4px 0.5px rgba(0, 0, 0, 0.15);

  white-space: nowrap;
}

.title-green {
  color: $color-green;
  box-shadow:
      0 4px 0 color.adjust($color-green, $lightness: -5%),
      0 0 0 5px $base-white;
}

.title-blue {
  color: $color-blue;
  box-shadow:
      0 4px 0 color.adjust($color-blue, $lightness: -5%),
      0 0 0 5px $base-white;
}

.title-red {
  color: $color-red;
  box-shadow:
      0 4px 0 color.adjust($color-red, $lightness: -5%),
      0 0 0 5px $base-white;
}
</style>

