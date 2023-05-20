<template>
  <div>
    <main-vue />
  </div>
</template>

<script>
import mainVue from "./components/main.vue";

export default {
  name: "app",
  components: {
    mainVue: mainVue,
  },
};
</script>

<style>
body {
  background-image: url("./assets/home/background-home-tablet.jpg");
  background-repeat: no-repeat;
  width: 100vw;
  height: 100vh;
}
</style>
