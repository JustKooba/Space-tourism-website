<template>
  <header-vue v-on:listClick="listClick" />

  <div class="content main-cont" :style="{ display: contentDisplay }">
    <h2 class="home-subtitle">So, you want to travel to</h2>
    <h1 class="home-title">Space</h1>
    <p class="home-desc">
      Let’s face it; if you want to go to space, you might as well genuinely go
      to outer space and not hover kind of on the edge of it. Well sit back, and
      relax because we’ll give you a truly out of this world experience!
    </p>
    <button class="explore" @click="handleExplore">Explore</button>
  </div>
  <div class="destinations">
    <destinations-vue :style="{ display: destDisplay }" />
  </div>
  <div class="crew" :style="{ display: crewDisplay }">
    <crew-vue />
  </div>
  <div class="technology" :style="{ display: techDisplay }">
    <technology-vue />
  </div>
</template>

<script>
import headerVue from "./header.vue";
import destinations from "./destinations.vue";
import crewVue from "./crew.vue";
import technology from "./technology.vue";
export default {
  components: {
    "header-vue": headerVue,
    "destinations-vue": destinations,
    "crew-vue": crewVue,
    "technology-vue": technology,
  },
  data() {
    return {
      contentDisplay: "none",
      destDisplay: "none",
      crewDisplay: "none",
      techDisplay: "flex",
    };
  },
  methods: {
    listClick(clickedEl) {
      console.log(clickedEl);
      if (clickedEl == "Home") {
        this.contentDisplay = "flex";
        this.destDisplay = "none";
        this.crewDisplay = "none";
      } else if (clickedEl == "Destination") {
        this.contentDisplay = "none";
        this.destDisplay = "flex";
        this.crewDisplay = "none";
      } else if (clickedEl == "Crew") {
        this.contentDisplay = "none";
        this.destDisplay = "none";
        this.crewDisplay = "flex";
      }
    },
    handleExplore() {
      this.contentDisplay = "none";
      this.destDisplay = "flex";
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
  display: flex;
}

.main-cont {
  height: 100vh;
  width: 100vw;
  background-image: url("../assets/home/background-home-tablet.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

@media screen and (max-height: 680px) {
  .main-cont {
    background-image: url("../assets/home/background-home-mobile.jpg");
  }
}

@media screen and (min-width: 681px) {
  .main-cont {
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
  margin-top: 100px;
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
