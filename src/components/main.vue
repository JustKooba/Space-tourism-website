<template>
  <header-vue />
  <div class="content" :style="{ display: contentDisplay }">
    <h2 class="home-subtitle">So, you want to travel to</h2>
    <h1 class="home-title">Space</h1>
    <p class="home-desc">
      Let’s face it; if you want to go to space, you might as well genuinely go
      to outer space and not hover kind of on the edge of it. Well sit back, and
      relax because we’ll give you a truly out of this world experience!
    </p>
    <button class="explore">Explore</button>
  </div>
  <div class="destinations">
    <destinations-vue v-on:listClick="listClick" />
  </div>
</template>

<script>
import headerVue from "./header.vue";
import destinations from "./destinations.vue";
export default {
  components: {
    "header-vue": headerVue,
    "destinations-vue": destinations,
  },
  data() {
    return {
      contentDisplay: "none",
    };
  },
  methods: {
    listClick() {
      if () {
        this.contentDisplay = "flex";
      }
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
@import url("https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@200&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Barlow&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Barlow&family=Bellefair&display=swap");
body {
  background-image: url("../assets/home/background-home-tablet.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  width: 100vw;
  height: 100vh;
  display: flex;
}

@media screen and (max-height: 680px) {
  body {
    background-image: url("../assets/home/background-home-mobile.jpg");
  }
}

@media screen and (min-width: 681px) {
  body {
    background-image: url("../assets/home/background-home-desktop.jpg");
  }
}

.home-subtitle,
.home-desc {
  color: #a9aab8;
  text-align: center;
}
.home-desc {
  line-height: 30px;
  font-size: 20px;
  text-align: center;
  padding: 12px;
  font-family: "Barlow", sans-serif;
}
.home-subtitle {
  text-transform: uppercase;
  margin-bottom: 5px;
  font-size: 25px;
  letter-spacing: 2px;
  font-family: "Barlow Condensed", sans-serif;
}

.home-title {
  color: white;
  text-align: center;
  text-transform: uppercase;
  font-family: "Bellefair", sans-serif;
  font-size: 80px;
  letter-spacing: 12px;
  margin-bottom: 10px;
  margin-top: 15px;
}

.explore {
  border-radius: 50%;
  border: none;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 200px;
  width: 200px;
  font-size: 35px;
  text-transform: uppercase;
  font-family: "Bellefair", sans-serif;
  font-weight: 400;
  margin-top: 10rem;
  cursor: pointer;
  transition: 0.3s ease-in-out;
}

.explore:active {
  transform: scale(0.9);
  transition: ease-in-out 0.1s;
}

@media (max-width: 400px) {
  .explore {
    margin-top: -0.2rem;
    height: 170px;
    width: 170px;
  }
}

.content {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;

  transition: 0.3s ease-in-out;
}
</style>
