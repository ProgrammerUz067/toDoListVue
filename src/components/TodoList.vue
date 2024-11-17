<template>
  <div>
    <div>
      <input
        v-model="newTask"
        @keyup.enter="addTask"
        placeholder="Add a new task"
      />
      <button @click="addTask">Add</button>
    </div>
    <ul>
      <TodoItem
        v-for="(task, index) in tasks"
        :key="index"
        :task="task"
        :index="index"
        @delete-task="deleteTask"
        @toggle-complete="toggleComplete"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: {
    TodoItem,
  },
  data() {
    return {
      tasks: [],
      newTask: "",
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim()) {
        this.tasks.push({ text: this.newTask, completed: false });
        this.newTask = "";
      }
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    toggleComplete(index) {
      this.tasks[index].completed = !this.tasks[index].completed;
    },
  },
};


</script>

<style scoped>
input {
  padding: 5px;
  width: 200px;
  font-size: 1rem;
}
button {
  padding: 5px 10px;
  margin-left: 5px;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
