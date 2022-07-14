<template>
  <div>
    <h1> {{ msg }} </h1>

    <div id="addRecipe">
      <h2>Add a new recipe</h2>
      <form @submit.prevent="addRecipe">
        <input v-model="newTitle" size="70" placeholder="Enter title here">
        <br>
        <input v-model="newIngredients" size="70" placeholder="Enter ingredients here">
        <br>
        <input v-model="newInstructions" size="70" placeholder="Enter instructions here">
        <br><br>
        <div>
          <button>Add Recipe</button>
        </div>
      </form>
    </div>

    <div id="showRecipes">
      <h2>View recipes</h2>
      <li v-for="recipe in recipes" :key="recipe.title">
        <div id="recipe">
          --{{ recipe.title }}--
          <br>
          Ingredients: {{ recipe.ingredients }} 
          <br>
          Instructions: {{ recipe.instructions }} 
          <br>
          <button @click="removeRecipe(recipe)">Delete</button>
        </div>
        <br><br>
      </li>
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
      newTitle: '',
      newIngredients: '',
      newInstructions: '',
      recipes: [
        { title: 'Banana Milkshake', ingredients: '2 bananas and 1 cup of milk', instructions: 'Pour milk and banana slices into a blender then blend until it is liquid' },
        { title: 'Ham Sandwich', ingredients: '1 slice of bread and 1 slice of ham', instructions: 'Put the slice of ham on top of the slice of bread and then fold the bread' },
        { title: 'Cheese Toastie', ingredients: '2 slices of bread, 1 slice of cheese and butter', instructions: 'Butter the the slices of bread and put the cheese slice between them, then toast until golden' }
      ],
    }
  },
  methods: {
    addRecipe() {
      if(this.newTitle != '' && this.newIngredients != '' && this.newInstructions != ''){
        this.recipes.push({ title: this.newTitle, ingredients: this.newIngredients })
      this.newTitle = ''
      this.newIngredients = ''
      this.newInstructions = ''
      }
    },
    removeRecipe(recipe) {
      this.recipes = this.recipes.filter((t) => t !== recipe)
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
