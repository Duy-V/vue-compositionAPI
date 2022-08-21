<template>
  <div>
    <h1>THIS IS ABOUT PAGE</h1>
    <button @click="goToContact">Go to Contact Page</button>
  </div>
</template>
<script>
import { useRouter } from "vue-router";
export default {
  name: "About",
  setup() {
    const router = useRouter();
    function goToContact() {
      router.push("/contact");
    }
    return { goToContact };
  },
};
</script>
