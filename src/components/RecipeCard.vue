<script>
    export default {
      props: {
        recipe: {
          type: Object,
          default() {
            return {};
          }
        },
        selectedTags: {
          type: Array,
          default() {
            return [];
          }
        }
      }
    };
    </script>

<template>
  <div class="recipe-card">
    <h2>{{ recipe.title }}</h2>
    <p>Ingredients:</p>
    <ul>
      <li v-for="(ingredient, index) in recipe.ingredients" :key="index">
        {{ ingredient }}
      </li>
    </ul>
    <p>Instructions:</p>
    <ol>
      <li v-for="(instruction, index) in recipe.instructions" :key="index">
        {{ instruction }}
      </li>
    </ol>
    <p>Tags:</p>
    <span v-for="(tag, index) in selectedTags" :key="index" class="tag">
      {{ tag }}
    </span>
  </div>
</template>