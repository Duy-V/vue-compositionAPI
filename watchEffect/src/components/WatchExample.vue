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
import { ref, watchEffect } from "vue";

export default {
  name: "WatchExample",
  setup() {
    const name = ref("");
    const email = ref("");
    watchEffect(() => {
      console.log(name.value);
      console.log(email.value);
    });
    // điểm khác biệt giữa watch và wathEffect là khi watchEffect fresh thì watchEffect sẽ móc lại ngay trỏng màn hình console.log tức là được móc khi DOM được mounted những nó không chạy ngay lập trức khi component được mounted mà nó chỉ theo dõi các giá trị, còn watch khi fresh thì watch sẽ không được móc lại trỏng màn hình console.log. Tuy nhiên bạn cũng có thể nói watch chạy ngay lập tức như watchEffect với third argument

    // watch(
    //   [name, email],
    //   ([newName, newEmail], [prevName, prevEmail]) => {
    //     console.log("newName:", newName);
    //     console.log("newEmail:", newEmail);
    //     console.log("oldName:", prevName);
    //     console.log("oldEmail:", prevEmail);
    //     console.log(name.value);
    //     console.log(email.value);
    //   },
    //   { immediated: true }
    // );
    return {
      name,
      email,
    };
  },
};
</script>
