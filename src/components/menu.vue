<template lang="pug">
  .bg-white(class="w-100 h-32")
    .flex.pt-6(class="flex-col sm:flex-col md:flex-row lg:flex-row")
      .mx-auto.flex(class="lg:w-3/6 md:w-full sm:w-full sm:flex-col md:flex-row lg:flex-row flex-col")
        .mx-auto(class="lg:w-3/6 md:w-100 sm:w-100")
          g-link.text-3xl.font-medium(to="/") Arturo Guerrero
        .mx-auto(class="lg:w-3/6 md:w-100 sm:w-100")
          p.mx-2.text-3xl.font-light Ingles
      .mx-auto.flex.justify-end(class=" my-4 md:my-0 lg:my-0 lg:w-2/6 md:w-100 sm:w-100")
        div.mx-4
          font-awesome.mx-2(:icon="['fas', 'moon']")
          //- switches.mx-2(v-model="light" v-on:click="test()" theme="bulma" color="red")
          //- font-awesome.mx-2(:icon="['fas', 'sun']")
          font-awesome.mx-2(:icon="['fab', 'instagram']")
          font-awesome.mx-2(:icon="['fab', 'facebook']")
          font-awesome.mx-2(:icon="['fab', 'github']")

</template>

<script>
import Switches from 'vue-switches'

export default {
  components: { Switches },
  data() {
    return {
      light: false,
    }
  },
  watch: {
    light() {
      this.test()
    },
  },
  methods: {
    test() {
      console.log(this.light)
    },
  },
}
</script>

<style>
svg {
  width: 23px !important;
  height: 23px !important;
}
</style>
