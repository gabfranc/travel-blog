<script setup>
const { data: post } = await useFetch("/api/blog", {
  headers: useRequestHeaders(["cookie"]),
});
</script>
<template>
  <main></main>
  <div>
    <ul>
      <li v-for="(blogs, index) in posts" :key="index">
        <NuxtLink :to="`/blogs/${blogs.slug}`">{{ blogs.title }}</NuxtLink>
      </li>
    </ul>
  </div>
  <button type="button"><NuxtLink to="/">HOME</NuxtLink></button>
</template>
<style>
h1 {
  text-align: center;
  font-size: 50px;
}
h2 {
  text-align: center;
}
p {
  text-align: start;
  margin: 100px;
}
button {
  border-radius: 12px;
  background: #7fb0d7;
  border: none;
  height: 5vh;
  width: 12vh;
}
</style>
