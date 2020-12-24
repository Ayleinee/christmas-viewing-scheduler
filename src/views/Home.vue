<template>
  <div class="home">
    <div class="home-selection">
      <button :class="showActive('24')" type="button" name="button" @click="setView('24')">Christmas Eve</button>
      <button :class="showActive('25')" type="button" name="button" @click="setView('25')">Christmas</button>
    </div>
    <div class="show-slot-div">
      <ShowSlot v-show="showView('24')" v-for="(show, index) in tv_json.shows" :time="show.time" :show="show.show" v-bind:key="index"></ShowSlot>
      <ShowSlot v-show="showView('25')" v-for="(show, index) in tv_json_2.shows" :time="show.time" :show="show.show" v-bind:key="index + '_1'"></ShowSlot>
    </div>
  </div>
</template>

<script>
import TVJSON from "./../json/show.json";
import TVJSON2 from "./../json/show-2.json";
import ShowSlot from "./../components/ShowSlot.vue";

export default {
  name: 'Home',
  data(){
    return{
      tv_json: TVJSON,
      tv_json_2: TVJSON2,
      VIEW: "24"
    }
  },
  methods:{
    showView:function(select){
      return (this.VIEW == select);
    },
    showActive:function(select){
      if(this.VIEW == select)
        return "active";

      return "";
    },
    setView:function(set){
      this.VIEW = set;
    }
  },
  components:{
    ShowSlot
  }
}
</script>

<style>
  .home{
    display: block;
    padding: 30px;
  }

  .home-selection{
    width: 100%;
    height: 40px;
    margin-bottom: 10px;
  }

  .show-slot-div{

    height: 80vh;
    overflow-y: scroll;
  }

  .active{
    background-color: #e497a8;
    color: white;
    font-weight: bold;
  }

  button{
    background: white;
    width: auto;
    height: 100%;
    padding: 10px 14px;
    margin-left: 10px;
    margin-right: 10px;
    border: none;
    font-size: 16px;
    border-radius: 8px;
    color: #dec3c3;
  }
</style>
