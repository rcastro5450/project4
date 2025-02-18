<template>
  <div class="ingredient-list">
    <div class="ingredient-input-container">
      <input 
        v-model="ingredient" 
        @keyup.enter="addIngredient" 
        placeholder="Add an ingredient..." 
        class="ingredient-input"
      />
      <input 
        v-model.number="calories" 
        type="number" 
        placeholder="Calories" 
        class="calories-input"
      />
      <button @click="addIngredient" class="add-btn">Add Ingredient</button>
    </div>

    <ul>
      <li v-for="(item, index) in ingredients" :key="index" class="ingredient-item">
        {{ item.name }} - {{ item.calories }} calories
        <button @click="removeIngredient(index)" class="delete-btn">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ingredient: '',
      calories: null,
      ingredients: []
    };
  },
  methods: {
    addIngredient() {
      if (this.ingredient.trim() !== '' && this.calories !== null) {
        this.ingredients.push({ name: this.ingredient, calories: this.calories });
        this.ingredient = '';
        this.calories = null;
        this.$emit('update-total-calories', this.totalCalories);
      }
    },
    removeIngredient(index) {
      this.ingredients.splice(index, 1);
      this.$emit('update-total-calories', this.totalCalories);
    }
  },
  computed: {
    totalCalories() {
      return this.ingredients.reduce((sum, item) => sum + item.calories, 0);
    }
  }
};
</script>