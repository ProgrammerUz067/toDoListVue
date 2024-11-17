<template>
  <div id="app">
    <h1>Vue To-Do List</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  components: {
    TodoList,
  },
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f9f9f9;
  text-align: center;
  margin: 0;
  padding: 0;
}
h1 {
  color: #333;
}
</style>
