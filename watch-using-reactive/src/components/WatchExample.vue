<template>
  <h2>Watchers in Vue 3</h2>
  <!-- <input type="text" v-model="search" /> -->
  <input type="text" v-model="search.query" />
  {{ search.query }}
</template>
<script>
import { watch, reactive } from "vue";

// import { ref, watch, reactive } from "vue";
export default {
  name: "WatchExample",
  setup() {
    // const search = ref("");
    const search = reactive({
      query: "",
    });

    watch(
      () => search.query,
      (newSearch, prevSearch) => {
        console.log("search", newSearch, prevSearch);
      }

      //   search,
      //   (newSearch, prevSearch) => {
      //       console.log("search", newSearch, prevSearch);
      //   }
    );

    return {
      search,
    };
  },
};
</script>
