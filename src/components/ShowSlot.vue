<template>
  <div class="show-slot">
    <div class="time">
      {{time}}
    </div>
    <div class="show">
      {{show}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  props:["time", "show"],
  data(){
    return{
    }
  },
  mounted:function(){
    // console.log("time: " + this.time);
  }
}
</script>

<style>
  .show-slot{
    /* background-color: white; */
    display: flex;
    flex-flow: row nowrap;
    height: 50px;
    margin-bottom: 12px;
    color: white;
    font-size: 18px;
  }

  .time{
    display: flex;
    background-color: #4097b1;
    width: 200px;
    border-radius: 10px;
    margin-right: 16px;
    justify-content: center;
    align-items: center;
  }

  .show{
    display: flex;
    background-color: #5fb4cd;
    border-radius: 10px;
    flex: auto;
    align-items: center;
    padding-left: 20px;
  }
</style>
