<template>
  <page>
    <h1>My Anime Tier List</h1>
    <boxes>
      <div v-for="rank in ranks" v-bind:key="rank.id">
        <h2>{{ rank }} Tier</h2>
        <h3>Search bar goes here</h3>
        <box-styling>
          <Box/>
        </box-styling>
      </div>
    </boxes>
  </page>
</template>

<script>
import Box from './Box.vue'
export default {
  components: { Box },
  name: 'HelloWorld',
  data: function () {
    return {
      ranks: ["S", "A", "B", "C","D","F"],
      animes: ["Attack on Titan","Sword Art Online"],
    }
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1{
  font-family:Lucida Console;
  color: black;
  font-size:80px;
  text-align:center;
}
h2{
  font-family:Courier New;
  color: black;
  font-size:50px;
  text-align:center;
}
h3{
  font-family:Courier New;
  color: black;
  font-size:20px;
  text-align:center;
}
box-styling{
  border: 10px solid #989999;
  border-radius: 10px;
  background-color: #C2C6C6;
  width:1400px;
  height:700px;
  display: flex;
}
boxes{
  display: flex;
  align-items: center;
  flex-direction: column;
}
page {
  color: blue; 
}
</style>
