<template lang="pug">
  div
    g-link(:to="data.path")
      g-image(class="border-4 hover:border-pink" :alt="data.alt" :src="data.image.src")
    g-link(class="hover:text-pink text-2xl my-2" :to="data.path") {{data.title}}
    p.text-base.my-2.font-base {{data.datetime}}
    //- p.text-base.my-4.font-base {{data.desc}}
</template>

<script>
export default {
  props: ['data'],
}
</script>

<style></style>
