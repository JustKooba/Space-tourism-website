<template>
  <div class="content tech-cont">
    <h2 class="pick"><span class="num tech">03</span>SPACE LAUNCH 101</h2>

    <div class="tech-desc" v-if="selectedTech">
      <img :src="getImagePath(selectedTech.images.landscape)" alt="Image" />

      <div class="buttons">
        <button
          class="tech-btn"
          :class="{ active: selectedTech.name === 'Launch vehicle' }"
          @click="selecttech('Launch vehicle')"
        >
          1
        </button>
        <button
          class="tech-btn"
          :class="{ active: selectedTech.name === 'Spaceport' }"
          @click="selecttech('Spaceport')"
        >
          2
        </button>
        <button
          class="tech-btn"
          :class="{ active: selectedTech.name === 'Space capsule' }"
          @click="selecttech('Space capsule')"
        >
          3
        </button>
      </div>
      <h3 class="tech-name">{{ selectedTech.name }}</h3>
      <p class="tech-description">{{ selectedTech.description }}</p>
    </div>
  </div>
</template>

<script>
import data from "../assets/data.json";

export default {
  data() {
    return {
      tech: [],
      selectedTech: null,
    };
  },
  mounted() {
    this.tech = data.technology;
    this.selectedTech = this.tech.find(
      (tech) => tech.name === "Launch vehicle"
    );
  },
  methods: {
    getImagePath(image) {
      return require(`../assets/technology/${image}`);
    },
    selecttech(techName) {
      this.selectedTech = this.tech.find((tech) => tech.name === techName);
    },
  },
};
</script>

<style>
.tech-cont {
  background-image: url("../assets/technology/background-technology-tablet.jpg");
  height: 100vh;
  width: 100vw;
  overflow-y: hidden;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

h2 {
  color: #fff;
  font-family: "Bellefair", sans-serif;
  text-transform: uppercase;
  text-align: center;
  font-size: 19px;
}

.num {
  color: #707070;
}

.tech-desc img {
  height: 180px;
}
.tech-desc {
  color: #d0d6f9;
  margin-top: -20px;
  font-size: 23px;
  padding: 25px;
}

.tech-btn {
  border-radius: 50%;
  border: none;
  height: 30px;
  width: 30px;
  background: transparent;
  border: 1px solid #fff;
  color: #fff;
}

.tech-name {
  font-size: 30px;
  color: #fff;
  margin-top: 10px;
  margin-bottom: 10px;
}

.tech-btn.active {
  background-color: #fff;
  color: black;
}

.image-wrapper div {
  position: relative;
  margin: auto;
  height: 1px;
  width: 80vw;
  background-color: #707070;
}
</style>
