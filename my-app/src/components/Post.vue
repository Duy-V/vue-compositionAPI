<template>
  <div>
    <h1>THIS IS POST PAGE</h1>
    <div>Post Page</div>
    <div>Post id: {{ id }}</div>
    <router-link to="/post/leela">Go to leela Post</router-link>
    <!-- <button @click="goToContact">Go to Contact Page</button> -->
  </div>
</template>
<script>
import { ref, watch } from "vue";
import { useRoute } from "vue-router";
export default {
  name: "Post",
  setup() {
    const id = ref("");
    const route = useRoute();
    id.value = route.params.id;
    watch(
      () => route.params.id,
      () => {
        id.value = route.params.id;
      }
    );
    return { id };
  },
};
</script>
