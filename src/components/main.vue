<template>
  <div class="menu">
    <img src="../assets/shared/icon-hamburger.svg" alt="three lines, menu" />

    <div class="menu-content">00 Home 01 Destination 02 Crew 03 Technology</div>
  </div>
  <div class="content">
    <h2 class="home-subtitle">So, you want to travel to</h2>
    <h1 class="home-title">Space</h1>
    <p class="home-desc">
      Let’s face it; if you want to go to space, you might as well genuinely go
      to outer space and not hover kind of on the edge of it. Well sit back, and
      relax because we’ll give you a truly out of this world experience!
    </p>
    <button class="explore">Explore</button>
  </div>
</template>

<script>
export default {};
</script>

<style>
@font-face {
  font-family: majesty-display;
  src: url("../assets/fonts/Majesty Bold.ttf");
}

@import url("https://fonts.googleapis.com/css2?family=Lato:wght@100;300&display=swap");
body {
  background-image: url("../assets/home/background-home-tablet.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  width: 100vw;
  height: 100vh;
}

@media screen and (max-height: 680px) {
  body {
    background-image: url("../assets/home/background-home-mobile.jpg");
  }
}

@media screen and (min-width: 681px) {
  body {
    min-height: 100vh;
    min-width: 100vw;
    background-image: url("../assets/home/background-home-desktop.jpg");
  }
}

.home-subtitle,
.home-desc {
  color: #a9aab8;
  text-align: center;
  font-family: "lato", sans-serif;
  line-height: 30px;
}
.home-desc {
  font-size: 20px;
}
.home-subtitle {
  text-transform: uppercase;
  text-align: left;
  margin-bottom: 15px;
  font-size: 22px;
  font-weight: 100;
  margin-right: 20px;
}

.home-title {
  color: #fff;
  text-align: center;
  text-transform: uppercase;
  font-family: "majesty-display", sans-serif;
  font-size: 100px;
  letter-spacing: 25px;
  margin-bottom: 20px;
  margin-top: 15px;
}

.explore {
  border-radius: 50%;
  border: none;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 170px;
  width: 170px;
  font-size: 30px;
  text-transform: uppercase;
  font-family: "lato", sans-serif;
  font-weight: 400;
  margin-top: 20vh;
}

.content {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 20px;
}

.menu-content {
  display: none;
}
</style>
