<template lang="pug">
  div
    g-link(:to="data.path")
      g-image(class="border-4 hover:border-pink" :alt="data.alt" :src="data.image.src")
    g-link(:to="data.path")
      p.text-lg.my-4.font-medium {{data.title}}
    p.text-base.my-4.font-light {{data.datetime}}
    p.text-base.my-4.font-base {{data.desc}}
</template>

<script>
export default {
  props: ['data'],
}
</script>

<style></style>
