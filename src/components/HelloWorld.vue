<template>
  <div id="hello">
    <p>这里是{{data.city}}天气</p>
    <p>{{data.WD}}：{{data.WSE}}</p>
    <p>气压：{{data.AP}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Vue.js Project!",
      data: {}
    };
  },
  created() {
    fetch("/data/sk/101110101.html")
      .then(response => response.json())
      .then(data => {
        this.data = data.weatherinfo;
      });
  },
  methods: {
    onclick() {
      console.log(this.data);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#hello{
	text-align: center;
}
</style>
