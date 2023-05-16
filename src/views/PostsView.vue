<script setup lang="ts">
import { RouterLink, useRoute } from 'vue-router'
import { watch } from 'vue'

let currentPage = useRoute()?.query?.page || 0;

watch(useRoute(), ({query})=>{
  if(query.page){
    currentPage = query.page;
  }
});

</script>

<template>
  <div class="main">
    <div class="TextPart">
      <RouterLink :to="{ path: '/'}">{{'<'}} Back</RouterLink>
      <h2>Post #{{ currentPage }}</h2>
      <h4>13/06</h4>
      
    </div>
    <div class="linksPart">
      <div class="wrapper">
        <h1>Posts</h1>
        <nav>
          <span :key="n" v-for="n in 10">
            <RouterLink active-class="active" :to="{ path: '/posts', query: { page: n} }">Post {{ n }} - 13/06</RouterLink>
          </span>
        </nav>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.main {
  min-height: 100vh;
  display: flex;
  justify-content: space-between;
  background-color: #623D87;
  color:#E4F7FF;
}

.TextPart {
  margin-top: 20px;
  margin-left: 27px;
  a{
    color:#E4F7FF;
    font-weight: 700;
  }
  h2 {
    width: 30vw;
    font-size: 3.07vw;
  }

  @media (max-width: 768px) {
    h2 {
      font-size: 23.57px;
    }
  }

  @media (min-width: 1756px) {
    h2 {
      width: 526.5px;
      font-size: 53.9px;
    }
  }
}

.linksPart {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 24.45vw;
  max-width: 452px;
  background-color: #483D87;

  h3 {
    height: 100%;
    display: flex;
  }

  .wrapper {
    background-color: #FFF312;
    width: 20vw;
    height: 100%;
    max-width: 288px;
    text-align: center;

    nav {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      span {
        margin-bottom: 10px;
      }

      a:hover {
        font-size: 2.4vw;
      }
    }
  }

  h1 {
    color: #263034;
    font-size: 3vw;
    font-weight: bold;
    margin: 25px 0px;
  }

  a {
    text-decoration: none;
    color: #263034;
    font-size: 1.6vw;
    transition: font-size 0.2s;
    font-weight: bold;
    @media (min-width:1440px) {
      font-size: 29px;
    }
  }
}
</style>
