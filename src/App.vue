<template>
  <div id="app">
    <header>
      <h1>Minha Lista de Tarefas</h1>
    </header>
    <task-list :tasks="tasks" @addTask="addTask" @removeTask="removeTask" />
  </div>
</template>

<script>
import TaskList from "./components/TaskList.vue";

export default {
  data() {
    return {
      tasks: [],
    };
  },
  components: {
    TaskList,
  },
  methods: {
    addTask(task) {
      this.tasks.push(task);
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
@import "@/assets/styles.css";
</style>

