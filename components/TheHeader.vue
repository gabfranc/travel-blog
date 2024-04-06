<template>
  <header>
    <div>
      <img src="../public/Logo.png" alt="Logo-Image" />
    </div>

    <nav>
      <ul>
        <li><NuxtLink to="/">HOME</NuxtLink></li>
        <li><NuxtLink to="/articles">Post</NuxtLink></li>
        <li><NuxtLink to="/sign-up">Sign-up</NuxtLink></li>
        <li><NuxtLink to="/login">Login</NuxtLink></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
nav ul {
  display: flex;
  flex-direction: row;
  gap: 10vh;
  justify-content: center;
  text-align: center;
}
img {
  height: 8vh;
  width: 27vh;
}
</style>
