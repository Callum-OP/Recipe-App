<template>
  <div>
    {{ msg }}

    <div id="addRecipe">
      <p>Add a new recipe</p>
      <input :value="text" placeholder="Enter title here">
      <br><br>
      <input :value="text" placeholder="Enter ingredients here">
      <br><br>
      <div>
        <button> Add </button>
      </div>
    </div>

    <div id="showRecipes">
    <p>View recipes</p>
    <ul>
      <li v-for="recipe in recipes" :key="recipe.title">
        {{ recipe.title }} :
        {{ recipe.ingredients }}
        <br><br>
      </li>
    </ul>
    </div>

  </div>
</template>

<script>
export default {
  name: 'RecipeApp',
  props: {
    msg: String
  },
  data() {
    return {
      recipes: [
        { title: 'Banana Milkshake', ingredients: '2 bananas and 1 cup of milk' },
        { title: 'Ham Sandwich', ingredients: '1 slice of bread and 1 slice of ham' }
      ],
    }
  },
  methods: {
    add(){
      
    }
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
