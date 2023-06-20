<template>
  <div class="content">
    <h2 class="pick"><span class="num dest">02</span>Meet your crew</h2>
  </div>
</template>

<script>
import data from "../assets/data.json";

export default {
  data() {
    return {
      destinations: [],
      selectedDestination: null,
    };
  },
  mounted() {
    this.destinations = data.destinations;
    this.selectedDestination = this.destinations.find(
      (destination) => destination.name === "Moon"
    );
  },
  methods: {
    getImagePath(image) {
      return require(`../assets/destination/${image}`);
    },
    selectDestination(destinationName) {
      this.selectedDestination = this.destinations.find(
        (destination) => destination.name === destinationName
      );
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
