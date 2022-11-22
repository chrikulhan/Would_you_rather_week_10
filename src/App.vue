<template>
  <div id="app">
<!--    template child must have *exactly* one element
**you can put ANYThing you want inside this div, but can only have
this one div.-->
    <h1>Would you rather... </h1>
<!--    you MUST have closed tags when using vue-->
<!--How to access components in -->
  </div>
  </template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
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
</style>
