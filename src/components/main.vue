<template>
  <header>
    <img src="../assets/shared/logo.svg" />
    <div class="menu">
      <img
        src="../assets/shared/icon-hamburger.svg"
        class="menu-img"
        alt="three lines, menu"
      />

      <div class="menu-content">
        00 Home 01 Destination 02 Crew 03 Technology
      </div>
    </div>
  </header>

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
@import url("https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@200&display=swap");
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
}
.home-desc {
  line-height: 30px;
  font-size: 20px;
  text-align: center;
  padding: 12px;
  font-family: "Barlow", sans-serif;
}
.home-subtitle {
  text-transform: uppercase;
  margin-bottom: 5px;
  font-size: 25px;
  letter-spacing: 2px;
  font-family: "Barlow Condensed", sans-serif;
}

.home-title {
  color: white;
  text-align: center;
  text-transform: uppercase;
  font-family: "Bellefair", sans-serif;
  font-size: 80px;
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
  height: 200px;
  width: 200px;
  font-size: 35px;
  text-transform: uppercase;
  font-family: "Bellefair", sans-serif;
  font-weight: 400;
  margin-top: 10rem;
  cursor: pointer;
}

.explore:active {
  transform: scale(0.9);
  transition: ease-in-out 0.1s;
}

@media (max-width: 400px) {
  .explore {
    margin-top: -0.2rem;
    height: 170px;
    width: 170px;
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

.menu img {
  cursor: pointer;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  margin-bottom: 25px;
}
</style>
