<template lang="pug">
  div
    Menu
    div(class="lg:w-3/4 md:w-3/4 sm:w-100 mx-auto")
      .flex.my-16(class="lg:w-2/4 md:w-full sm:w-full justify-center sm:justify-center md:justify-start lg:justify-start")
        button.mx-2.pb-2(class="border-b-4 hover:border-pink text-lg" v-on:click="by(true)"  v-bind:class="[type ? 'border-pink' : 'border-transparent']") Publicaciones
        button.mx-2.pb-2(class="border-b-4 hover:border-pink text-lg" v-on:click="by(false)" v-bind:class="[type ? 'border-transparent' : 'border-pink']") Temas
    .grid-themes(v-show="type" class="w-3/4 ml-auto mr-auto")
      GridPost(v-for="i in $page.allPost.edges" :key="i.node.id" :data="i.node")
    List(v-show="!type" title="Simple Present" class="w-5/6 lg:w-2/4 md:w-3/4 sm:w-5/6 mx-auto" :data="$page.allPost")
</template>

<page-query>
query{
  allPost{
    edges{
      node{
        id
        path
        title
        category
        datetime: date (format: "YYYY-MM-DD")
        image
        image_caption
        desc
      }
    }
  }
}
</page-query>

<script>
import Switches from 'vue-switches'
import Menu from '../components/menu'
import List from '../components/List'
import GridPost from '../components/GridPost'
import Footer from '../components/Footer'
export default {
  components: { Switches, Menu, List, GridPost, Footer },
  data() {
    return {
      type: true,
    }
  },
  methods: {
    by(data) {
      if (this.type != data) this.type = data
    },
  },
}
</script>

<style>
svg {
  width: 23px !important;
  height: 23px !important;
}
.grid-themes {
  display: grid;
  grid-template: auto/repeat(3, 1fr);
  gap: 50px;
}
body {
  background-color: #ecf0f1;
}
@media (max-width: 1024px) {
  .grid-themes {
    grid-template: auto/repeat(2, 1fr);
  }
}
@media (max-width: 768px) {
  .grid-themes {
    grid-template: auto/repeat(1, 1fr);
  }
}
</style>
