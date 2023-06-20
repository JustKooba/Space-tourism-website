<template>
  <div class="content">
    <h2 class="pick"><span class="num dest">02</span>Meet your crew</h2>

    <div class="person-desc" v-if="selectedPerson">
      <img :src="getImagePath(selectedPerson.images.png)" alt="Image" />
      <div class="buttons">
        <button
          class="person-btn"
          @click="selectPerson('Douglas Hurley')"
        ></button>
        <button
          class="person-btn"
          @click="selectPerson('Mark Shuttleworth')"
        ></button>
        <button
          class="person-btn"
          @click="selectPerson('Victor Glover')"
        ></button>
        <button
          class="person-btn"
          @click="selectPerson('Anousheh Ansari')"
        ></button>
      </div>
      <h4>{{ selectPerson.role }}</h4>
      <h3>{{ selectedPerson.name }}</h3>
      <p class="p-desc">{{ selectedPerson.bio }}</p>
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
</style>
