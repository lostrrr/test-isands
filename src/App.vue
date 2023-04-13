<template>
  <AppHeader />
  <AppCompare />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AppHeader from "./components/AppHeader.vue";
import AppCompare from "./components/AppCompare.vue";

export default defineComponent({
  name: "App",
  components: {
    AppHeader,
    AppCompare,
  },
});
</script>

<style>
* {
  font-family: "Roboto", sans-serif;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
a {
  text-decoration: none;
}
.container {
  width: 1100px;
  margin: 0 auto;
}
</style>
