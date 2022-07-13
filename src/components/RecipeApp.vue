<template>
  <div>
    {{ msg }}

    <div id="addRecipe">
      <p>Add a new recipe</p>
      <input type="text" id="recipe">
      <input type="submit" value="Add">
    </div>

    <div id="showRecipes">

    </div>

  </div>
</template>

<script>
export default {
  name: 'RecipeApp',
  props: {
    msg: String
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
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
