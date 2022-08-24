<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld />
    <GoodNight />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import GoodNight from './components/GoodNight'

export default {
  name: 'App',
  components: {
    HelloWorld,
    GoodNight
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
