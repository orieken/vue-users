<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div class="wrapper min-h-screen bg-gray-400 antialiased text-gray-900">
    <users></users>
  </div>
</template>

<script>
import Users from "./components/Users";

export default {
  name: "App",
  components: {
    Users,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
