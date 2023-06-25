<template>
  <div class="content crew-cont">
    <h2 class="pick"><span class="num dest">02</span>Meet your crew</h2>

    <div class="person-desc" v-if="selectedPerson">
      <span class="image-wrapper">
        <img :src="getImagePath(selectedPerson.images.png)" alt="Image" />
        <div></div>
      </span>
      <div class="buttons">
        <button
          class="person-btn"
          :class="{ active: selectedPerson.name === 'Douglas Hurley' }"
          @click="selectPerson('Douglas Hurley')"
        ></button>
        <button
          class="person-btn"
          :class="{ active: selectedPerson.name === 'Mark Shuttleworth' }"
          @click="selectPerson('Mark Shuttleworth')"
        ></button>
        <button
          class="person-btn"
          :class="{ active: selectedPerson.name === 'Victor Glover' }"
          @click="selectPerson('Victor Glover')"
        ></button>
        <button
          class="person-btn"
          :class="{ active: selectedPerson.name === 'Anousheh Ansari' }"
          @click="selectPerson('Anousheh Ansari')"
        ></button>
      </div>
      <h4>{{ selectedPerson.role }}</h4>
      <h3 class="person-name">{{ selectedPerson.name }}</h3>
      <p class="person-bio">{{ selectedPerson.bio }}</p>
    </div>
  </div>
</template>

<script>
import data from "../assets/data.json";

export default {
  data() {
    return {
      crew: [],
      selectedPerson: null,
    };
  },
  mounted() {
    this.crew = data.crew;
    this.selectedPerson = this.crew.find(
      (crew) => crew.name === "Douglas Hurley"
    );
  },
  methods: {
    getImagePath(image) {
      return require(`../assets/crew/${image}`);
    },
    selectPerson(crewName) {
      this.selectedPerson = this.crew.find((crew) => crew.name === crewName);
    },
  },
};
</script>

<style>
.crew-cont {
  background-image: url("../assets/crew/background-crew-tablet.jpg");
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

h4 {
  color: #6c757d;
  font-family: "Barlow Condensed", sans-serif;
  text-transform: uppercase;
  font-size: 20px;
  margin-top: 20px;
}

.num {
  color: #707070;
}

.person-desc img {
  height: 230px;
}
.person-bio {
  color: #d0d6f9;
  margin-top: -20px;
  font-size: 23px;
  padding: 25px;
}

.person-btn {
  border-radius: 50%;
  border: none;
  height: 10px;
  width: 10px;
  background-color: #6c757d;
}

.person-name {
  font-size: 30px;
  color: #fff;
  margin-top: 10px;
  margin-bottom: 10px;
}

.person-btn.active {
  background-color: #fff;
}

.image-wrapper div {
  position: relative;
  margin: auto;
  height: 1px;
  width: 80vw;
  background-color: #707070;
}
</style>
