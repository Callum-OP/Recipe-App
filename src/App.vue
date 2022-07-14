<template>
  <div id="app">
    <RecipeApp msg="Welcome to the Recipe App"/>
  </div>
</template>

<script>
import RecipeApp from './components/RecipeApp.vue'

export default {
  name: 'App',
  components: {
    RecipeApp
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
