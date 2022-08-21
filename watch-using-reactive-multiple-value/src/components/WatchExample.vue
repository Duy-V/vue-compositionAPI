<template>
  <div>
    <h1>Watchers in Vue 3</h1>
    <div>
      Name:
      <input type="text" v-model="name" />
      <p>name: {{ name }}</p>
    </div>
    <div>
      Email:
      <input type="text" v-model="email" />
      <p>Email: {{ email }}</p>
    </div>
  </div>
</template>
<script>
import { ref, watch } from "vue";

export default {
  name: "WatchExample",
  setup() {
    const name = ref("");
    const email = ref("");
    watch([name, email], ([newName, newEmail], [prevName, prevEmail]) => {
      console.log("newName:", newName);
      console.log("newEmail:", newEmail);
      console.log("oldName:", prevName);
      console.log("oldEmail:", prevEmail);
      console.log(name.value);
      console.log(email.value);
    });
    return {
      name,
      email,
    };
  },
};
</script>
