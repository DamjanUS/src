<template>
  <div>
    <h1>Recipe List</h1>
    <ul>
      <li v-for="recipe in recipes" :key="recipe.id">
        <button @click="selectRecipe(recipe)">{{ recipe.name }}</button>
      </li>
    </ul>
    <RecipeDetails
      v-if="this.selectedRecipe"
      :recipe="this.selectedRecipe"
      class="recipes"
    />
  </div>
</template>

<script>
import RecipeDetails from "./RecipeDetails.vue";
export default {
  name: "RecipeList",
  components: {
    RecipeDetails,
  },
  props: {
    recipes: Array,
  },
  data() {
    return {
      recipes: [
        {
          id: 1,
          name: "Spaghetti Bolognese",
          ingredients: ["Spaghetti", "Beef", "Tomato Sauce"],
          instructions: ["Cook spaghetti. Brown beef. Add sauce."],
        },
        {
          id: 2,
          name: "Chicken Curry",
          ingredients: ["Chicken", "Curry Powder", "Coconut Milk"],
          instructions: ["Cook chicken. Add curry powder. Add coconut milk."],
        },
        {
          id: 3,
          name: "Beef Stroganoff",
          ingredients: ["Beef", "Mushrooms", "Sour Cream"],
          instructions: ["Cook beef. Add mushrooms. Stir in sour cream."],
        },
      ],
      selectedRecipe: null,
    };
  },
  methods: {
    selectRecipe(recipe) {
      this.selectedRecipe = recipe;
    },
  },
};
</script>

<style scoped>
.recipes {
  border: 1px solid;
  border-radius: 10px;
  box-shadow: 0 0 8px #ebdfdff6;
  padding: 25px;
  width: 25%;
}
</style>
