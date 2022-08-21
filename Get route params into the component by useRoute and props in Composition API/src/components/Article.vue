<template>
  <div>
    <h1>THIS IS ARTICLE PAGE</h1>
    <div>Article id : {{ id }}</div>
    <div>
      <router-link to="article/leela">Go to leela article</router-link>
    </div>
    <!-- <button @click="goToContact">Go to Contact Page</button> -->
  </div>
</template>
<script>
export default {
  name: "Article",
};
</script>
