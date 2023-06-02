<template>
  <div class="content">
    <h2><span class="num dest">01</span>Pick your destination</h2>
    <div class="destination">
      <img src="" alt="" />
    </div>
  </div>
</template>

<script>
import data from "../assets/data.json";
export default {
  data() {
    return {
      data: data,
    };
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
