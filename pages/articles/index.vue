<script setup>
import { ref } from 'vue';
const supabase = useSupabaseClient();
const user = useSupabaseUser();
const router = useRouter();
const { data: blogs } = await useAsyncData("blogs", async () => {
  const { data } = await supabase.from("blogs").select("*");
  return data;

})

//DONE: Make blog post appear when the nuxtlink is clicked
const showBlog = ref(false);

//DONE: Create Function to make the blog popup
const openBlog = () => {
  showBlog.value = true;
};

//DONE: Create function to close the blog pop up

const closeBlog = () => {
  showBlog.value = false;
};
</script>
<template>
  
  <section>
    <ul>
      <li v-for="(blog, index) in blogs" :key="index">
        <NuxtLink :to="blog" @click="openBlog">{{ blog.title }}</NuxtLink>
       <div v-if="showBlog" class="popup">
        <div class="blog-content">
          <h2>{{ blog.title }}</h2>
          <p>{{ blog.description }}</p>

          <button @click="closeBlog">Close Blog</button>
        </div>
       </div>
    </li>
    </ul>
  </section>
</template>
<style scoped>
  button {
    cursor: pointer;
  }
</style>