<template lang="pug">
  div(class="w-full bg-white border-b-8 border-t border-black mt-16")
    div.my-16.text-center
      font-awesome.mx-2(:icon="['fas', 'moon']")
      //- switches.mx-2(v-model="light" v-on:click="test()" theme="bulma" color="red")
      //- font-awesome.mx-2(:icon="['fas', 'sun']")
      font-awesome.mx-2(:icon="['fab', 'instagram']")
      font-awesome.mx-2(:icon="['fab', 'facebook']")
      font-awesome.mx-2(:icon="['fab', 'github']")
      p.mt-8 Hecho con amor 
      font-awesome.text-pink(:icon="['fas', 'heart']")

</template>

<script>
export default {}
</script>

<style></style>
