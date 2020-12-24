<template>
  <div id="app">
    <!-- <h1>Viewing Schedule: 12/24/20</h1> -->
    <Snowf class="snow-fall"
    :amount="50"
    :size="5"
    :speed="1.5"
    :wind="0"
    :opacity="0.8"
    :swing="1"
    :image="null"
    :zIndex="null"
    :resize="true"
    color="#fff"
    />
    <router-view/>

    <div class="dragonite"></div>
    <div class="snow-left"></div>
    <div class="snow-right"></div>
    <div class="snow-flat"></div>
    <div class="snow-man"></div>

  </div>
</template>

<script>
import Snowf from 'vue-snowf';

export default {
  name: 'Home',
  data(){
    return{
    }
  },
  components:{
    Snowf
  }
}
</script>

<style lang="scss">
html, body{
  background: #8bd5ea;
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 30px;
}

.dragonite{
  position: absolute;
  left: 10px;
  top: 10px;
  background-image: url("./assets/dragonnite.png");
  background-color: transparent;
  width: 104px;
  height: 104px;
}

.snow-fall{
  pointer-events:none;
}

.snow-left{
  position: absolute;
  left: 0px;
  bottom: 0px;
  background-image: url("./assets/snow-left.png");
  background-color: transparent;
  width: 109px;
  height: 245px;
}

.snow-right{
  position: absolute;
  right: 0px;
  bottom: 0px;
  background-image: url("./assets/snow-right.png");
  background-color: transparent;
  width: 100px;
  height: 230px;
}

.snow-man{
  position: absolute;
  right: 100px;
  bottom: 8px;
  background-image: url("./assets/snowman.png");
  background-color: transparent;
  width: 121px;
  height: 173px;
}

.snow-flat{
  position: absolute;
  display: block;
  bottom: 0px;
  background-image: url("./assets/snow-flat.png");
  background-color: transparent;
  width: 100%;
  padding: 0;
  margin: 0;
  left: 0;
  height: 76px;
}
</style>
