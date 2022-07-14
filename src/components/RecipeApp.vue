<template>
  <div>
    {{ msg }}

    <div id="addRecipe">
      <p>Add a new recipe</p>
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
    <p>View recipes</p>
    <ul>
      <li v-for="recipe in recipes" :key="recipe.title">
        <p>
          {{ recipe.title }} :
          {{ recipe.ingredients }} 
          <button @click="removeRecipe(recipe)">Delete</button>
        </p>
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
        { title: 'Ham Sandwich', ingredients: '1 slice of bread and 1 slice of ham' }
      ],
    }
  },
  methods: {
    addRecipe() {
      this.recipes.push({ title: this.newTitle, ingredients: this.newIngredients })
      this.newTitle = ''
      this.newIngredients = ''
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
