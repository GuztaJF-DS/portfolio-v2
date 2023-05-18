<script setup lang="ts">
  import { computed, toRefs } from 'vue';
  const props = defineProps<{
    index: number,
    revert?: boolean,
  }>()
  const { index, revert } = toRefs(props);

  const RoundStyle = computed(()=>{
  let style:any = { top: index.value*7 + 'vw'}
  if(revert.value){
    style={...style, transform: 'rotate(45deg)', backgroundColor:"#0C4173"}
  }

  return style
});
</script>

<template>
  <div class="Round" :style="RoundStyle">
  </div>
</template>

<style scoped lang="scss">
.Round{
  height: 2.5vw;
  width: 2.5vw;
  background-color: #623D87;
  left: 0.1vw;
  clip-path: polygon(0% 0%, 100% 100%, 0% 100%);
  transform: rotate(-135deg);
  /* Round */
  /* border-radius: 0 0 0 1em; */
  /* Jigsaw */
  border-radius: 1em 0 1em 1em;
}

</style>