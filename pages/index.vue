<script setup>
import Hero from "~/components/Hero.vue";
const { data: posts } = await useFetch("/pages/blog", {
  headers: useRequestHeaders(["cookie"]),
});
</script>
<template>
  <main>
    <Hero />

    <div>
      <p>
        Welcome to Hidden Gems! This is your go-to travel blog website full of
        joy and adventures. Whether you are seeking inspiration for your next
        getaway or practical tips for navigating new destinations, we've got you
        covered. Hidden Gems is a virtual treasure trove of firsthand travel
        experiences, expert recommendations, and captivating stories from
        globetrotters around the world.
      </p>
    </div>
    <button type="button"><NuxtLink to="blogs">Blogs</NuxtLink></button>
 </main>
</template>
<style scoped>
p {
  justify-content: center;
  text-align: center;
}
</style>
