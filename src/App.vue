<script setup lang="ts">
import { RouterView } from 'vue-router'
const rightColor = '#0C4173'
const leftColor = '#0C4173'
</script>



<template>
  <div class="main">
    <div class="Left"></div>
    <div class="Right"></div>
    <div class="RouterClass">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
  .main{
    display: flex;
    justify-content: center;
    height: 100vh;
  }
  .Left{
    background-color: v-bind('leftColor');
    width: 50vw;
  }
  .Right{
    background-color:  v-bind('rightColor');
    width: 50vw;
  }
  .RouterClass{
    position: absolute;
    width: 100%;
    max-width: 1440px;
  }
</style>
