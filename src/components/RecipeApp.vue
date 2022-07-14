<template>
  <div>
    <h1> {{ msg }} </h1>

    <div id="addRecipe">
      <h2>Add a new recipe</h2>
      <form @submit.prevent="addRecipe">
        <input v-model="newTitle" placeholder="Enter title here">
        <br><br>
        <input v-model="newIngredients" placeholder="Enter ingredients here">
        <br><br>
        <div>
          <button>Add Recipe</button>
        </div>
      </form>
    </div>

    <div id="showRecipes">
      <h2>View recipes</h2>
      <ul>
        <li v-for="recipe in recipes" :key="recipe.title">
          <div id="recipe">
            {{ recipe.title }} :
            {{ recipe.ingredients }} 
            <button @click="removeRecipe(recipe)">Delete</button>
          </div>
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
      newTitle: '',
      newIngredients: '',
      recipes: [
        { title: 'Banana Milkshake', ingredients: '2 bananas and 1 cup of milk' },
        { title: 'Ham Sandwich', ingredients: '1 slice of bread and 1 slice of ham' },
        { title: 'Grilled Cheese Sandwich', ingredients: '1 slice of bread and 1 slice of cheese' }
      ],
    }
  },
  methods: {
    addRecipe() {
      if(this.newTitle != '' && this.newIngredients != ''){
        this.recipes.push({ title: this.newTitle, ingredients: this.newIngredients })
      this.newTitle = ''
      this.newIngredients = ''
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
