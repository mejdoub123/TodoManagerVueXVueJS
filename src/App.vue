<template>
  <NavBar />
  <router-view />
</template>
<script>
import NavBar from "./components/NavBar.vue";
export default {
  components: {
    NavBar,
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Source+Code+Pro&display=swap");
body {
  margin: 0;
  background-color: #f5f7fb;
  font-family: "Source Code Pro", monospace;
}
</style>
