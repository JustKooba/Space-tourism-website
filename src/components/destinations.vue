<template>
  <div class="content">
    <h2 class="pick"><span class="num dest">01</span>Pick your destination</h2>

    <div class="destination-desc" v-if="selectedDestination">
      <img :src="getImagePath(selectedDestination.images.png)" alt="Image" />
      <div class="buttons">
        <button class="dest-btn" @click="selectDestination('Moon')">
          Moon
        </button>
        <button class="dest-btn" @click="selectDestination('Mars')">
          Mars
        </button>
        <button class="dest-btn" @click="selectDestination('Europa')">
          Europa
        </button>
        <button class="dest-btn" @click="selectDestination('Titan')">
          Titan
        </button>
      </div>
      <h3>{{ selectedDestination.name }}</h3>
      <p>{{ selectedDestination.description }}</p>
      <div class="distance"></div>
    </div>
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
.content {
  width: 100vw;
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

.dest {
  font-size: 19px;
}

.pick {
  margin-bottom: 25px;
}

.destination-desc img {
  height: 180px;
}

.dest-btn {
  background: transparent;
  border: none;
  font-family: "Barlow Condensed", sans-serif;
  font-size: 20px;
  font-weight: 700;
  text-transform: uppercase;
  color: #fff;
  display: flex;
}

.buttons {
  margin-top: 20px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 30px;
}

.buttons button:hover {
  text-decoration: underline;
  cursor: pointer;
}

.destination-desc {
  color: #fff;
}
</style>
