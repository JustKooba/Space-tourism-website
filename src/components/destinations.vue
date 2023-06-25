<template>
  <div class="content dest-cont">
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
      <p class="p-desc">{{ selectedDestination.description }}</p>
      <div class="distance">
        <p class="avg-distance">Avg Distance</p>
        <p class="avg-distance-num">{{ selectedDestination.distance }}</p>
        <p class="travel">Est travel time</p>
        <p class="travel-num">{{ selectedDestination.travel }}</p>
      </div>
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
  height: 100vh;
}

.dest-cont {
  background-image: url("../assets/destination/background-destination-tablet.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

@media screen and (max-height: 680px) {
  .dest-cont {
    background-image: url("../assets/destination/background-destination-mobile.jpg");
  }
}

@media screen and (min-width: 681px) {
  .dest-cont {
    background-image: url("../assets/destination/background-destination-desktop.jpg");
  }
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
  margin-top: 80px;
}

.destination-desc img {
  height: 170px;
}

.dest-btn {
  background: transparent;
  border: none;
  font-family: "Barlow Condensed", sans-serif;
  font-size: 20px;
  font-weight: 700;
  text-transform: uppercase;
  color: #d0d6f9;
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

h3 {
  font-size: 60px;
  font-family: "Bellefair", sans-serif;
  text-transform: uppercase;
  margin-top: 20px;
}

.p-desc {
  color: #d0d6f9;
  margin-top: -20px;
  font-size: 23px;
  padding: 25px;
  border-bottom: 1px solid #d0d6f9;
}

.avg-distance-num {
  font-size: 33px;
}

.avg-distance {
  margin-top: 20px;
  font-size: 18px;
  color: #d0d6f9;
  text-transform: uppercase;
}

.travel {
  text-transform: uppercase;
  margin-top: 10px;
  font-size: 18px;
  color: #d0d6f9;
  text-transform: uppercase;
}

.travel-num {
  font-size: 33px;
}
</style>
