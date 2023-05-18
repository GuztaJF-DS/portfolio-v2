<script setup lang="ts">
import SpikeBorder from '../components/SpikeBorder.vue'
</script>

<template>
  <div class="Container" :key="n" v-for="n in 23">
    <SpikeBorder :index=n-1 />
  </div>
</template>

<style scoped lang="scss">
.Container {
  top: 0px;
  z-index: 0;
  position: absolute;
  left:18.7vw;
  height: 100%;
  width: 200px;
  display: flex;
  overflow-y: hidden;
  justify-content: flex-start;
  flex-direction: column;
}
</style>