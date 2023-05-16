<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="main">
    <div class="TextPart">
        <h2>Prazer, meu nome é Gustavo</h2>
        <h1>Um Dev Full-Stack </h1>
      </div>
    <div class="linksPart">
      <div class="wrapper">
        <nav>
          <RouterLink active-class="active" to="/about">Sobre Mim</RouterLink>
          <RouterLink to="/projects">Projetos</RouterLink>
          <RouterLink to="/posts">Posts</RouterLink>
          <RouterLink to="/studies">Estudos</RouterLink>
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
    color:#E4F7FF;
  }
  .TextPart {
    margin: 20px;
    h2 {
      margin-left: 7px;
      width:30vw;
      font-size: 3.07vw;
    }
    h1 {
      margin-top: 150px;
      font-weight: 600;
      margin-left: 30px;
      font-size: 5vw;
    }
    @media (max-width: 768px) {
      h2 {
        font-size: 23.57px;
      }
      h1 {
        font-size: 38px;
      }
    }
    @media (min-width: 1756px) {
      h2 {
        width:526.5px;
        font-size: 53.9px;
      }
      h1 {
        font-size: 87.8px;
      }
    }
  }
  .linksPart{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 31.45vw;
    max-width: 452px;
    h3{
      height: 100%;
      display: flex;
    }

    a { 
      text-decoration: none;
      color:#263034;
      font-size: 2vw;
      transition: font-size 0.2s;
      font-weight: bold;
      @media (min-width:1440px) {
        font-size: 29px;
      }
    }
  }

  .wrapper {
    background-color: #FFF312;
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

  @media (max-width:622px){
    .main{
      justify-content: flex-end;
      flex-direction:column-reverse;
    }

    .TextPart{
      h2 {
        width: 200px;
      }
      h1 {
        margin-top: 40px;
      }
    }

    .linksPart{
      width: 100vw;
      max-width: 100vw;
      a { 
        @media (max-width:425px) {
          font-size: 5vw;
        }
        font-size: 4vw;
      }
    }

    .wrapper{
      width: 90vw;
      min-height: 145px;
      justify-content: flex-end;
      max-width: 90vw;
      nav {
        z-index: 2;
        top: 10px;
        position: relative;
        :hover{
          font-size: 4.4vw;
          @media (max-width:425px) {
            font-size: 5.8vw;
          }
        }
      }
    }
    .triangle{
      border-left: 45vw solid transparent;
      border-right: 45vw solid transparent;
      border-top: 10vw solid #FFF312;
    }
  }
</style>
