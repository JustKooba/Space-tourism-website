<template>
  <div class="content">
    <h2 class="pick"><span class="num dest">01</span>Pick your destination</h2>
    <div class="destination" v-if="destinations.length > 0">
      <img :src="getImagePath(destinations[0].images.png)" alt="Image" />
    </div>
    <div class="buttons">
      <button class="dest-btn">Moon</button>
      <button class="dest-btn">Mars</button>
      <button class="dest-btn">Europa</button>
      <button class="dest-btn">Titan</button>
    </div>

    <div
      class="destination-desc"
      v-for="destination in destinations"
      :key="destination"
    >
      <h3>{{ destination.name }}</h3>
      <p>{{ destination.description }}</p>
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
    };
  },
  mounted() {
    this.destinations = data.destinations;
  },
  methods: {
    getImagePath(image) {
      return require(`../assets/destination/${image}`);
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

.destination img {
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
