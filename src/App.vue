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
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
