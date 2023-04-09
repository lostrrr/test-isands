<template>
  <AppHeader :totalItems="totalItems" :itemList="itemList" />
  <AppCompare :totalItems="totalItems" :itemList="itemList" />
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppCompare from "./components/AppCompare.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppCompare,
  },
  data() {
    return {
      itemList: [],
    };
  },
  computed: {
    totalItems() {
      return this.itemList.length;
    },
  },
};
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
