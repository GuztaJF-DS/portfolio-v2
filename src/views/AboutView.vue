<script setup lang="ts">
  import RoundWall from '../components/RoundWall.vue'
</script>

<template>
  <div class="MainContainer">
    <div class="leftSide">
      AboutPosting
      <RoundWall />
    </div>
  </div>
</template>

<style scoped lang="scss">
  .leftSide {
    height: 100vh;
    width: 20vw;
    background-color: #623D87;
    z-index: 2;
  }
  .MainContainer {
    display: flex;
    flex-direction: row;
    background-color: #0C4173;
  }
</style>
