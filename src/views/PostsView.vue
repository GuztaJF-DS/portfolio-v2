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
      <h3>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed egestas dignissim erat non congue. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nulla blandit risus auctor metus malesuada aliquet. Sed placerat consequat dapibus. Proin tincidunt ligula nec dignissim vulputate. In hac habitasse platea dictumst. Nullam nec condimentum augue. Maecenas eu lobortis nunc. Nulla facilisi. Donec at magna sed nisl ullamcorper vulputate. Nunc interdum turpis eu condimentum vulputate. Vivamus a luctus lectus. Donec ut lacinia urna. Donec bibendum eros vel congue mattis. Praesent finibus tortor eget tortor eleifend, sit amet tristique lectus posuere.
          {{ "\n\n" }}Proin imperdiet mauris vel mi suscipit facilisis. Donec vitae nunc malesuada ex tincidunt euismod. Proin enim turpis, semper at lobortis nec, mollis eget elit. Cras auctor mi quis arcu sagittis finibus. Donec vulputate consequat dui, non lobortis lectus dignissim pellentesque. Nam ullamcorper interdum tortor eget commodo. Phasellus nec mi non nulla vestibulum dignissim a vehicula dui. Maecenas erat elit, dignissim sit amet fermentum in, malesuada a risus. Etiam vitae dignissim turpis. In aliquam mi eget auctor pretium. In suscipit odio purus. Morbi quis erat ut ipsum vehicula venenatis. In tempor nunc in enim consectetur ornare. Phasellus aliquet commodo erat, fermentum .
        </h3>
    </div>
    <div class="linksPart">
      <div class="wrapper">
        <h1>Posts</h1>
        <nav>
          <span :key="n" v-for="n in 20">
            <RouterLink active-class="active" :to="{ path: '/posts', query: { page: n} }">Post {{ n }} - 13/06</RouterLink>
          </span>
        </nav>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.main {
  max-height: 100vh;
  min-height: 100vh;
  display: flex;
  justify-content: space-between;
  background-color: #520F96;
  color:#E4F7FF;

  ::-webkit-scrollbar {
    display: none;
  }
}

.TextPart {
  margin-top: 20px;
  margin-left: 27px;
  width: 65%;
  
  overflow-y: auto;
  a{
    color:#E4F7FF;
    font-weight: 700;
  }
  h2 {
    width: 30vw;
    font-size: 3.07vw;
  }
  h3 {
    margin-top: 20px;
    overflow-wrap: break-word;
    white-space: pre-line;
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
  background-color: #41348b;

  h3 {
    height: 100%;
    display: flex;
  }

  .wrapper {
    background-color: #FFF312;
    width: 20vw;
    height: 100%;
    max-width: 288px;
    display: flex;
    flex-direction: column;
    text-align: center;

    ::-webkit-scrollbar {
      display: block;
      width: 10px;
    }
    ::-webkit-scrollbar-thumb {
      background: #bbb20f; 
    }

    h1 {
      color: #263034;
      margin: auto;
      font-size: 3vw;
      font-weight: bold;
      @media (min-width:1440px) {
        font-size: 43.17px;
      }
      @media (max-width: 768px) {
        font-size: 23.07px;
      }
    }

    nav {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      overflow-y: auto;
      max-height: 84%;
      span {
        margin-bottom: 0.5vw;
      }

      a:hover {
        font-size: 2.4vw;
        @media (min-width:1440px) {
          font-size: 33.56px;
        }
      }
    }
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

    @media (max-width: 768px) {
      font-size: 12.3px;
    }
  }
}
</style>
