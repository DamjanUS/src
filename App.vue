<template>
  <div id="app" style="padding: 20px; margin: 10px">
    <h1 style="margin-bottom: 50px">Recipe Book</h1>

    <RecipeList />
  </div>
</template>

<script>
import RecipeList from "./components/RecipeList.vue";

export default {
  name: "App",
  components: {
    RecipeList,
  },
};
</script>

<style>
/* Global styles */
body {
  margin: 0;
  font-family: "Arial", sans-serif;
  background-color: #f4f4f4;
  color: #333;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header {
  background-color: #4caf50;
  color: white;
  padding: 20px;
  text-align: center;
}

main {
  flex: 1;
  padding: 20px;
}

footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px;
}

h1 {
  margin: 0;
}

h2 {
  color: #4caf50;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin: 10px 0;
}

button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
  font-size: 16px;
}

button:hover {
  background-color: #45a049;
}
</style>
