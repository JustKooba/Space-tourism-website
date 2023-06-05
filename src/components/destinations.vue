<template>
  <div class="content">
    <h2><span class="num dest">01</span>Pick your destination</h2>
    <div class="destination" v-if="destinations.length > 0">
      <img :src="getImagePath(destinations[0].images.webp)" alt="Image" />
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
</style>
