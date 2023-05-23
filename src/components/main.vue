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
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

@import url("https://fonts.googleapis.com/css2?family=Barlow&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Barlow&family=Bellefair&display=swap");
body {
  background-image: url("../assets/home/background-home-tablet.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  width: 100vw;
  height: 100vh;
  display: flex;
}

@media screen and (max-height: 680px) {
  body {
    background-image: url("../assets/home/background-home-mobile.jpg");
  }
}

@media screen and (min-width: 681px) {
  body {
    background-image: url("../assets/home/background-home-desktop.jpg");
  }
}

.home-subtitle,
.home-desc {
  color: #a9aab8;
  text-align: center;
  font-family: "Barlow", sans-serif;
}
.home-desc {
  line-height: 30px;
  font-size: 20px;
  text-align: center;
  padding: 7px;
}
.home-subtitle {
  text-transform: uppercase;
  margin-bottom: 5px;
  font-size: 16px;
  letter-spacing: 2px;
}

.home-title {
  color: #fff;
  text-align: center;
  text-transform: uppercase;
  font-family: "Bellefair", sans-serif;
  font-size: 70px;
  letter-spacing: 12px;
  margin-bottom: 10px;
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
  font-family: "Bellefair", sans-serif;
  font-weight: 400;
  margin-top: 10rem;
}

@media (max-width: 400px) {
  .explore {
    margin-top: 5rem;
  }
}

.content {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.menu-content {
  display: none;
}
</style>
