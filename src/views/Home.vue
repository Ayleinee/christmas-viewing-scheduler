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
// import TVJSON from "./../json/show.json";
// import TVJSON2 from "./../json/show-2.json";
import ShowSlot from "./../components/ShowSlot.vue";

export default {
  name: 'Home',
  data(){
    return{
      tv_json: {
        "shows":[
          {"time": "10:00 am", "show":"Last Holiday"},
          {"time": "11:30 am", "show":"The Simpsons Roasting on an Open fire"},
          {"time": "12:00 am", "show":"Frozen"},
          {"time": "01:00 pm", "show":"Futurama: Holiday special 1"},
          {"time": "01:30 pm", "show":"Bad Santa"},
          {"time": "02:00 pm", "show":"Batman Returns"},
          {"time": "03:30 pm", "show":"Charlie Brown Christmas Special"},
          {"time": "04:00 pm", "show":"Die Hard"},
          {"time": "06:00 pm", "show":"Frosty the Snowman"},
          {"time": "06:30 pm", "show":"Rise of the Guardians"},
          {"time": "08:00 pm", "show":"Jingle All the way"},
          {"time": "09:30 pm", "show":"Bob's Burgers The Bleakening"},
          {"time": "10:30 pm", "show":"Krampus"},
          {"time": "12:00 pm", "show":"Little Nicky"},
          {"time": "01:30 am", "show":"Family Guy Christmas special"},
          {"time": "10:00 am", "show":"Life and Adventure of Santa claus"},
          {"time": "11:30 am", "show":"Mickeys a Christmas carol"},
          {"time": "12:00 pm", "show":"Miracle on 34th street"},
          {"time": "01:40 pm", "show":"Jackie Chan Adventure Holiday"},
          {"time": "02:00 pm", "show":"Die Hard"},
          {"time": "03:00 pm", "show":"Happiest Season"},
          {"time": "04:40 pm", "show":"Planes trains and automobiles"},
          {"time": "06:00 pm", "show":"Proud family"},
          {"time": "06:20 pm", "show":"Prince of Egypt"},
          {"time": "08:00 pm", "show":"Tokyo godfathers"},
          {"time": "09:40 pm", "show":"Recess"},
          {"time": "10:00 pm", "show":"American dad holiday special"},
          {"time": "11:00 pm", "show":"Batman TAS Baby doll and Mr. Freeze"},
          {"time": "11:40 pm", "show":"Justice Leage"}
        ]
      },
      tv_json_2: {
        "shows":[
          {"time": "12:40 am", "show":"Futurama Holiday specials 2"},
          {"time": "01:20 am", "show":"Hey arnold"},
          {"time": "01:40 am", "show":"Justice league"},
          {"time": "02:00 am", "show":"Recess"},
          {"time": "02:40 am", "show":"South park"},
          {"time": "03:00 am", "show":"Simpsons holiday specials"}
        ]
      },
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
