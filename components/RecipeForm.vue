<template>
  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Recipe Name:</label>
      <input type="text" id="name" v-model="newRecipe.name" required />
    </div>
    <div>
      <label for="ingredients">Ingredients:</label>
      <textarea
        id="ingredients"
        v-model="newRecipe.ingredients"
        placeholder="Enter each ingredient on a new line"
        required
      ></textarea>
    </div>
    <div>
      <label for="instructions">Instructions:</label>
      <textarea
        id="instructions"
        v-model="newRecipe.instructions"
        placeholder="Enter each instruction on a new line"
        required
      ></textarea>
    </div>
    <button type="submit">Add Recipe</button>
  </form>
</template>
<script>
export default {
  name: "AddRecipeForm",
  data() {
    return {
      newRecipe: {
        name: "",
        ingredients: "",
        instructions: "",
      },
    };
  },
  methods: {
    submitForm() {
      const ingredientsArray = this.newRecipe.ingredients
        .split("\n")
        .map((i) => i.trim())
        .filter(Boolean);
      const instructionsArray = this.newRecipe.instructions
        .split("\n")
        .map((i) => i.trim())
        .filter(Boolean);

      const recipe = {
        id: Date.now(),
        name: this.newRecipe.name,
        ingredients: ingredientsArray,
        instructions: instructionsArray,
      };

      this.$emit("add-recipe", recipe);

      this.newRecipe.name = "";
      this.newRecipe.ingredients = "";
      this.newRecipe.instructions = "";
    },
  },
};
</script>

<style>
form {
  border: 1px solid #ccc;
  padding: 16px;
  border-radius: 8px;
  width: 45%;
  margin-top: 16px;
}

form div {
  margin-bottom: 8px;
}

label {
  display: block;
  margin-bottom: 4px;
}

input,
textarea {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  background-color: #28a745;
  color: white;
  padding: 10px 15px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #218838;
}
</style>
