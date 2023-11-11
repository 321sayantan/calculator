<template>
  <div id="app">
    <h1>Calculator</h1>
    <calculator/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import calculator from './components/calculator.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    calculator
  }
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
h1{
  color: #fff;
}
body{
  overflow: hidden;
  height: 100vh;
  background: url('https://wallpapercave.com/dwp1x/wp7399818.jpg') no-repeat center center/cover;
    /* background: linear-gradient(100deg, rgba(2,0,36,1) 0%, rgba(9,9,121,1) 10%, rgba(0,212,255,1) 100%); */
}
</style>
