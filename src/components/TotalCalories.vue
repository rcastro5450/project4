<template>
  <div class="total-calories">
    <strong>Total Calories: {{ totalCalories }}</strong>
  </div>
</template>

<script>
export default {
  data() {
    return {
      totalCalories: 0
    };
  },
  props: {
    totalCaloriesFromParent: {
      type: Number,
      default: 0
    }
  },
  watch: {
    totalCaloriesFromParent(newVal) {
      this.totalCalories = newVal;
    }
  }
};
</script>
