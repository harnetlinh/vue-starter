<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Linh v-bind:msg_time="current_time"/>
  </div>
</template>

<script>
import Linh from "./components/HelloLinh.vue"
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Linh
  },
  created(){
    this.getCurrentTime();
  },
  data(){
    return {
      name: "Linh",
      current_time: ""
    }
  },
  methods: {
    getCurrentTime(){
      fetch("http://worldtimeapi.org/api/ip").then(response => {
        response.json().then(res => {
          console.log(res);
          this.current_time = res.datetime;
        })
      })
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
