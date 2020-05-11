<template lang="pug">
  div
    Header
    div(class="w-4/5 md:w-4/5 lg:w-2/4 xl:w-2/4 mx-auto text-center")
      h1.text-2xl.mt-32.font-light(class="sm:text-base md:text-5xl") {{$page.post.title}}
      p.text-pink.text-2xl.mt-8.mb-16.font-semibold {{$page.post.datetime}}
      g-image.mx-auto.mb-16(class="border-4" :alt="$page.post.alt" :src="$page.post.image.src")
    div(v-html="$page.post.content" class="w-3/4 mx-auto")
    Footer
</template>

<script>
import Header from '../components/menu'
import Footer from '../components/Footer'
export default {
  components: { Header, Footer },
}
</script>
<page-query>
query Post ($path: String) {
  post (path: $path) {
    id
    path
    title
    category
    datetime: date (format: "YYYY-MM-DD")
    image
    image_caption
    desc
    content
  }
}
</page-query>
<style>
body {
  background-color: #ecf0f1;
}
p {
  font-size: 1.3rem;
}
h1 {
  font-size: 2rem;
  font-weight: bold;
}
h2 {
  font-size: 1.8rem;
  font-weight: bold;
}
h3 {
  font-size: 1.6rem;
  font-weight: bold;
}
h4 {
  font-size: 1.5rem;
  font-weight: bold;
}
h5 {
  font-size: 1.4rem;
  font-weight: bold;
}
h6 {
  font-size: 1.35rem;
  font-weight: bold;
}
ol {
  list-style: decimal;
}
ul {
  list-style: disc;
}
pre {
  border-top: 1px solid black;
  border-bottom: 1px solid black;
  margin: 30px 0;
  padding: 10px 0;
}
</style>
