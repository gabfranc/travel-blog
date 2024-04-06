<script setup>
const route = useRoute();
 const supabase = useSupabaseClient();
  console.log(route.params.blog);
 const { data: blog } = await useAsyncData("blog", async () => {
   const { data } = await supabase
  .from("blogs")
  .select("*")
   .eq("slug", route.params.blog)
  .single();
  return data;
 })
</script>
<template>
  <div v-if="blog.value">
    <h2> {{ blog.value.title }}</h2>
    <p> {{ blog.value.description }}</p>
    <p>Blog Last Update: {{ blog.date_updated }}</p>
  </div>
  <!-- <main>
    <h1>{{ blog.title }}</h1>
    <p>{{ blog.content }}</p>
    <p>Blog Last Update: {{ blog.date_updated }}</p>
  </main> -->
</template>
<style>
main {
  max-width: 800px;
  margin: 0 auto;
}
</style>
