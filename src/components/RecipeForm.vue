<template>
  <div class="recipe-form">
    <textarea 
      v-model="recipeText" 
      placeholder="Write your recipe steps here..." 
      class="recipe-textarea"
    ></textarea>
    <button @click="createRecipe" class="create-btn">Create Recipe</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      recipeText: ''
    };
  },
  methods: {
    createRecipe() {
      console.log('Recipe Created: ', this.recipeText);
      // You can add more logic here to save or display the recipe
    }
  }
};
</script>
