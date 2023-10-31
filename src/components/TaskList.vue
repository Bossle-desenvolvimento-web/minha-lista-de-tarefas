<template>
  <div class="task-list">
    <div class="task">
      <input v-model="newTask" @keyup.enter="addTask" placeholder="Adicionar uma nova tarefa" />
    </div>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        {{ task }}
        <button @click="removeTask(index)">Remover</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["tasks"],
  data() {
    return {
      newTask: "",
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim() !== "") {
        this.$emit("addTask", this.newTask);
        this.newTask = "";
      }
    },
    removeTask(index) {
      this.$emit("removeTask", index);
    },
  },
};
</script>

<style>
  @import "@/assets/styles.css";
</style>
