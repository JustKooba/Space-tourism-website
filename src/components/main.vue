<template>
  00 Home 01 Destination 02 Crew 03 Technology So, you want to travel to Space
  Let’s face it; if you want to go to space, you might as well genuinely go to
  outer space and not hover kind of on the edge of it. Well sit back, and relax
  because we’ll give you a truly out of this world experience! Explore
</template>

<script>
export default {};
</script>

<style>
body {
  background-image: url("../assets/home/background-home-tablet.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  width: 100vw;
  height: 100vh;
}

@media screen and (max-height: 680px) {
  body {
    background-image: url("../assets/home/background-home-mobile.jpg");
  }
}

@media screen and (min-width: 681px) {
  body {
    min-height: 100vh;
    min-width: 100vw;
    background-image: url("../assets/home/background-home-desktop.jpg");
  }
}
</style>
