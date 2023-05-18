<script setup lang="ts">
import RoundBorder from '../components/RoundBorder.vue'
</script>

<template>
  <div class="Container" :key="n" v-for="n in 24">
    <RoundBorder :index=n-1 :revert=true />
    <RoundBorder :index=n-0.85 />
  </div>
</template>

<style scoped lang="scss">
.Container {
  top: 0px;
  position: absolute;
  height: 100%;
  width: 200px;
  left: 18.65vw;
  display: flex;
  overflow-y: hidden;
  justify-content: flex-start;
  flex-direction: column;
}
</style>