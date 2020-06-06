<template lang="pug">
  section(class="w-2/5" @mouseleave="show = false") 
    button.flex.justify-between.border-b(v-on:click="toggle()" class="w-full") 
      span.text-3xl.ml-4 {{select}}
      font-awesome.ml-8.down(:icon="['fas', 'sort-down']" size="2x")
    .absolute.bg-white.pt-2.w-full(v-if="show")
      button(class="py-2 hover:text-pink block w-full text-left" v-on:click="update('Todos')" v-if="select!='Todos'") 
        font-awesome.mr-4(:icon="['fas', 'circle']" size="xs")
        span(class="text-3xl") Todos
      button(class="hover:text-pink py-2 block w-full text-left" v-on:click="update('value 1')" v-if="select!='value 1'") 
        font-awesome.mr-4(:icon="['fas', 'circle']" size="xs")
        span.text-3xl value1
      button(class="hover:text-pink py-2 block w-full text-left" v-on:click="update('value 2')" v-if="select!='value 2'")
        font-awesome.mr-4(:icon="['fas', 'circle']" size="xs")
        span.text-3xl value 2
      button(class=" hover:text-pink py-2 block w-full text-left" v-on:click="update('value 3')" v-if="select!='value 3'")
        font-awesome.mr-4(:icon="['fas', 'circle']" size="xs")
        span.text-3xl value 3
</template>

<script>
export default {
  data() {
    return {
      select: 'All',
      show: false,
    }
  },
  methods: {
    update(data) {
      this.select = data
      this.show = !this.show
    },
    toggle() {
      this.show = !this.show
    },
  },
}
</script>

<style scoped>
button:focus {
  outline: 0;
}
</style>
