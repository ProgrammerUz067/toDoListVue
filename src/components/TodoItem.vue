<template>
  <li>
    <span
      :style="{ textDecoration: task.completed ? 'line-through' : 'none' }"
      @click="$emit('toggle-complete', index)"
    >
      {{ task.text }}
    </span>
    <button @click="$emit('delete-task', index)">Delete</button>
  </li>
</template>

<script>
export default {
  props: {
    task: Object,
    index: Number,
  },
};
</script>

<style scoped>
li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 10px 0;
  padding: 5px;
  border: 1px solid #ddd;
  border-radius: 5px;
  background-color: #fff;
  width: 60%;
  margin-left: 350px;
}
span {
  cursor: pointer;
}
button {
  background-color: #ff6b6b;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
}
button:hover {
  background-color: #ff5252;
}
</style>
