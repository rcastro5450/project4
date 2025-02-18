<template>
  <div class="app">
    <h1 class="title">Recipe Builder</h1>
    <IngredientList />
    <RecipeForm />
    <TotalCalories />
  </div>
</template>

<script>
import IngredientList from './components/IngredientList.vue'
import RecipeForm from './components/RecipeForm.vue'
import TotalCalories from './components/TotalCalories.vue'

export default {
  name: 'App',
  components: {
    IngredientList,
    RecipeForm,
    TotalCalories
  }
}
</script>