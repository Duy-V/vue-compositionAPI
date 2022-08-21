<template>
  <div>
    <h1>THIS IS CONTACT PAGE</h1>
    <button @click="goToAbout">Go to AboutPage</button>
  </div>
</template>
<script>
import { useRouter } from "vue-router";
export default {
  name: "Contact",
  setup() {
    const router = useRouter();
    function goToAbout() {
      router.push("/about");
    }
    return {
      goToAbout,
    };
  },
};
</script>
