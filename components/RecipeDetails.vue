<template>
  <div v-if="recipe">
    <h3>{{ recipe.name }}</h3>
    <p><strong>Ingredients:</strong></p>
    <ul>
      <li v-for="ingredient in recipe.ingredients" :key="ingredient">
        {{ ingredient }}
      </li>
    </ul>
    <p><strong>instructions:</strong></p>
    <ul>
      <li v-for="instruction in recipe.instructions" :key="instruction">
        {{ instruction }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "RecipeDetails",
  props: {
    recipe: {
      type: Object,
      required: true,
    },
  },
};
</script>
