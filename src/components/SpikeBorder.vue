<script setup lang="ts">
  import { computed, toRefs } from 'vue';
  const props = defineProps<{
    index: number,
    revert?: boolean,
  }>()
  const { index, revert } = toRefs(props);

  const SpikeStyle = computed(()=>{
  let style:any = { top: index.value*3.5 + 'vw'}
  if(revert.value){
    style={...style, transform: 'rotate(45deg)'}
  }

  return style
});
</script>

<template>
  <div class="Spike" :style="SpikeStyle">
  </div>
</template>

<style scoped lang="scss">
.Spike{
  height: 2.5vw;
  width: 2.5vw;
  background-color: #623D87;
  clip-path: polygon(0% 0%, 100% 100%, 0% 100%);
  transform: rotate(-135deg);
}
</style>