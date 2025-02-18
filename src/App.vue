<script>
export default {
  data() {
    return {
      recipe: {
        title: '',
        ingredients: '',
        instructions: ''
      },
      selectedTags: [],
      tags: []
    };
  },
  methods: {
    submitRecipe() {
      // Logic to create a new recipe (save to database, API call, etc.)
      console.log(this.recipe, this.selectedTags);
    }
  }
};
</script>

<template>
  <div class="recipe-builder">
    <h1>Create a new recipe:</h1>
    <form @submit.prevent="submitRecipe">
      <div class="form-group">
        <label for="title">Recipe Title:</label>
        <input v-model.trim="recipe.title" type="text" id="title" />
      </div>
      <div class="form-group">
        <label for="ingredients">Ingredients:</label>
        <textarea v-model.trim="recipe.ingredients" id="ingredients" rows="6"></textarea>
      </div>
      <div class="form-group">
        <label for="instructions">Instructions:</label>
        <textarea v-model.trim="recipe.instructions" id="instructions" rows="6"></textarea>
      </div>
      <div class="form-group">
        <label for="tags">Tags:</label>
        <select multiple v-model="selectedTags">
          <option v-for="(tag, index) in tags" :key="index" :value="tag">
            {{ tag }}
          </option>
        </select>
      </div>
      <button type="submit">Create Recipe</button>
    </form>
  </div>
</template>