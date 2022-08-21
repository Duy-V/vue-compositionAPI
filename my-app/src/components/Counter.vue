<template>
  <div>
    <h1>THIS IS COUTER PAGE</h1>
    <div>{{ counter }}</div>
  </div>
  <button @click.prevent="onIncrement()">Increment Counter</button>
</template>
<script>
export default {
  name: "Counter",
  setup() {
    const counter = computed(() => {
      return this.$store.state.counter;
    });
    function onIncrement() {
      this.$store.dispatch("increment");
    }
    return {
      counter,
      onIncrement,
    };
  },
};
</script>
