<script setup lang="ts">
import { RouterView } from 'vue-router';
import { watch, ref } from 'vue'
import { useRoute } from 'vue-router';
let rightColor = ref('');
let leftColor  = ref('');

function getTheColors(path: string) {
  switch (path) {
    case '/posts':
      leftColor.value = '#623D87';
      rightColor.value = '#483D87';
      break;
    case '/studies':
    case '/projects':
      leftColor.value = '#0C5473';
      rightColor.value = '#93162A';
      break;
    case '/about':
      leftColor.value = '#623D87';
      rightColor.value = '#0C4173';
      break;
    default:
      leftColor.value = '#0C4173';
      rightColor.value = '#0C4173';
      break;
  }
}

getTheColors(window.location.pathname)

watch(useRoute(), ({ path }) => {
  getTheColors(path);
});
</script>



<template>
  <div class="main" >
    <div class="Left" :style="{ backgroundColor: leftColor }"></div>
    <div class="Right" :style="{ backgroundColor: rightColor }"></div>
    <div class="RouterClass">
      <RouterView/>
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
    width: 50vw;
  }
  .Right{
    width: 50vw;
  }
  .RouterClass{
    position: absolute;
    width: 100%;
    max-width: 1440px;
  }
</style>
