<template lang="pug">
  section
    div(v-for="i in Object.keys(categories)")
      p.text-2xl.mt-16.mb-2.font-semibold {{i}}
      div.p-1.bg-pink
      div.list-grid
        .my-2(v-for="j in categories[i]")
          div.inline-block.bg-pink.w-2.h-2.mr-2
          g-link(class="border-b-4 text-lg border-transparent hover:border-pink" :to="j.path") {{ j.title }}
</template>

<script>
export default {
  props: ['title', 'data'],
  data() {
    return {
      categories: {},
    }
  },
  created() {
    for (let i in this.data.edges) {
      if (!this.categories[this.data.edges[i].node.category])
        this.categories[this.data.edges[i].node.category] = []
      this.categories[this.data.edges[i].node.category].push(
        this.data.edges[i].node
      )
    }
    console.log(this.categories)
  },
}
</script>

<style scoped>
.list-grid {
  display: grid;
  grid-template: auto/repeat(2, 1fr);
}
</style>
