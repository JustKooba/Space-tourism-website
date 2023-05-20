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
  max-width: 100vw;
  max-height: 100vh;
}

@media screen and (max-height: 680px) {
  body {
    background-image: url("./assets/home/background-home-mobile.jpg");
  }
}

@media screen and (min-width: 681px) {
  body {
    min-height: auto;
    background-image: url("./assets/home/background-home-desktop.jpg");
  }
}
</style>
