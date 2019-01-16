<template>
  <div class="hello">

  </div>
</template>

<script>
import axios from "axios";
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      data1:[]
    }
  },
  created(){
    this.add()
  },
  methods:{
    add:()=>{
      fetch("/data/sk/101110101.html")
      .then(response=> response.json())
      .then(data=> console.log(data))
       
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
