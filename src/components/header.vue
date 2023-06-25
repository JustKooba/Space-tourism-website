<template>
  <div class="header-wrapper">
    <header>
      <img src="../assets/shared/logo.svg" />
      <div class="menu">
        <img
          src="../assets/shared/icon-hamburger.svg"
          class="menu-img"
          alt="three lines, menu"
          @click="menuClick"
        />
        <div class="menu-wrapper">
          <div class="menu-content" :style="{ display: menuDisplay }">
            <img
              src="../assets/shared/icon-close.svg"
              alt="X Icon"
              @click="menuClick"
            />
            <ul>
              <li>
                <span class="num">00</span>
                <span @click="listClick">Home</span>
              </li>
              <li>
                <span class="num">01</span>
                <span @click="listClick">Destination</span>
              </li>
              <li>
                <span class="num">02</span>
                <span @click="listClick">Crew</span>
              </li>
              <li>
                <span class="num">03</span
                ><span @click="listClick">Technology</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuDisplay: "none",
    };
  },
  methods: {
    menuClick() {
      if (this.menuDisplay == "none") {
        this.menuDisplay = "flex";
      } else {
        this.menuDisplay = "none";
      }
    },
    listClick() {
      let clickedEl = event.target.innerText;
      console.log(clickedEl);
      this.menuDisplay = "none";
      this.$emit("listClick", clickedEl);
    },
  },
};
</script>

<style>
.menu {
  transition: all 0.3s ease-in-out;
  position: absolute;
  right: 20px;
  top: 1;
}
.menu-content {
  display: flex;
  color: #fff;
  position: fixed;
  background-color: rgba(27, 27, 27, 0.6);
  -webkit-backdrop-filter: blur(30px);
  backdrop-filter: blur(30px);
  top: 0;
  right: 0;
  width: 70vw;
  height: 100vh;
  z-index: 1;
  font-family: "Barlow Condensed", sans-serif;
  transition: all 0.3s ease-in-out;
  overflow-y: auto;
}

.menu-wrapper {
  transition: all 0.3s ease-in-out;
}
.menu-content ul {
  display: flex;
  flex-direction: column;
  list-style: none;
  font-size: 27px;
  margin-left: 35px;
  margin-top: 100px;
}

.menu-content ul li {
  margin-top: 2rem;
}

.menu-content ul li:hover {
  text-decoration: underline;
  cursor: pointer;
}

.menu-content img {
  height: 30px;
  position: absolute;
  top: 20px;
  right: 20px;
}

.menu img {
  cursor: pointer;
}

.num {
  font-weight: 700;
  font-size: 24px;
  font-family: "Bellefair", sans-serif;
  margin-right: 5px;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  margin-bottom: 25px;
  width: 100vw;
}

.header-wrapper {
  position: absolute;
}
</style>
