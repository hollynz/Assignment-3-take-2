<template>
  <!-- <transition name="page-fade-in" mode="in-out"> -->
  <div class="home-bg">
    <router-link :to="'/'" exact>
      <GeoffBackBtn/>
    </router-link>

    <div class="container">
      <div class="nz-outline">
        <img src="../../assets/geoff/nz-outline.png">
      </div>
      <div class="title">
        <h1 class="title-top">WELLINGTON</h1>
        <h2 class="sub-title">A MUSIC ENTHUSIAST'S GUIDE</h2>
        <div class="flex-center">
          <router-link :to="'/GeoffCategories'" exact>
            <button class="btn-yellow">GET STARTED</button>
          </router-link>
        </div>
      </div>
    </div>
  </div>
  <!-- </transition> -->
</template>

<script>
import GeoffBackBtn from "./GeoffBackBtn.vue";

export default {
  name: "Geoff",
  components: {
    GeoffBackBtn
  }
};
</script>

<style scoped src="./constants/customFonts.css">
</style>

<style scoped>
.home-bg {
  background-image: url(../../assets/geoff/home-bg.jpg);
  background-size: cover;
  background-position: center;
  width: 100vw;
  height: 100vh;
}

.title {
  position: absolute;
  top: 55%;
  right: 15%;
  font-family: "BigNoodleTitling", sans-serif;
}

.nz-outline {
  position: absolute;
  top: 15%;
  right: 30%;
}

.nz-outline img {
  height: 600px;
}

.title-top {
  text-align: center;
  color: #fff;
  font-size: 90px;
  line-height: 0.6;
}

.sub-title {
  color: #ffe96b;
  text-align: center;
  font-size: 51px;
}

.btn-yellow {
  font-family: "BigNoodleTitling", sans-serif;
  color: #222;
  font-size: 25px;
  background-color: #ffe96b;
  text-align: center;
  transform: scale(1);
  padding: 5px 60px;
  margin-top: 50px;
  border: none;
  border-radius: 10px;
  transition: all 0.2s linear;
}

.btn-yellow:hover {
  background-color: #3fcbca;
  color: #fff;
  transform: scale(1.1);
}

.flex-center {
  display: flex;
  justify-content: center;
  align-content: center;
}

@media only screen and (max-width: 1000px) {
  .home-bg {
    background-position: 30% 0%;
  }

  .title {
    right: 10%;
  }

  .nz-outline img {
    height: 500px;
  }
}

@media only screen and (max-width: 600px) {
  .nz-outline img {
    height: 400px;
  }

  .nz-outline {
    top: 5%;
    right: 25%;
  }

  .title {
    top: 60%;
  }

  .title-top,
  .sub-title {
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-color: black;
  }
}

@media only screen and (max-width: 400px) {
  .title-top {
    font-size: 75px;
  }

  .sub-title {
    font-size: 40px;
  }

  .nz-outline {
    right: 10%;
    top: 5%;
  }

  .nz-outline img {
    height: 350px;
  }

  .title {
    right: 4%;
    top: 45%;
  }
}
</style>
