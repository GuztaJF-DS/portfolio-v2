<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="main">
    <div class="left">
      <h1>Prazer, meu nome é Gustavo</h1>
    </div>
    <div class="right">
      <div class="wrapper">
        <nav>
          <RouterLink active-class="active" to="/about">Sobre Mim</RouterLink>
          <RouterLink to="/project">Projetos</RouterLink>
          <RouterLink to="/posts">Posts</RouterLink>
          <RouterLink to="/study">Estudos</RouterLink>
        </nav>
      </div>
      <div class="triangle"></div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  .main {
    min-height: 100vh;
    display: flex;
    justify-content: space-between;
    background-color: #0C4173;
  }
  .left {
    margin: 20px;
  }
  .right{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 31.45vw;
    max-width: 452px;
    h3{
      text-align: center;
      height: 100%;
      display: flex;
      align-items: flex-end;
    }
  }

  a { 
    text-decoration: none;
    color:#263034;
    font-size: 2vw;
    transition: font-size 0.2s;
    font-weight: bold;
    :active{
      color:red;
    }
    @media (min-width:1440px) {
      font-size: 29px;
    }
  }
  .wrapper {
    background-color: #FFF312;
    color: #263034;
    margin: 0px;
    width: 20vw;
    min-height: 275px;
    max-width: 288px;
    nav {
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      text-align: center;
      :hover{
        font-size: 2.4vw;
      }
    }
  }
  .triangle{
    border-left: 10vw solid transparent;
    border-right: 10vw solid transparent;
    border-top: 5vw solid #FFF312;

    @media (min-width:1440px) {
      border-left-width: 144px;
      border-right-width: 144px;
      border-top-width: 72.4px;
    }
  }
</style>
