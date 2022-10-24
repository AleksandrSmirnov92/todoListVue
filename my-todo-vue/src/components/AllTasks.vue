<script lang="ts">
import Task from "./Task.vue";
export default {
  name: "AllTasks",
  props: ["tasks", "changeCheckbox", "deleteTask"],

  components: {
    Task,
  },
  setup(props) {
    return {
      Task,
    };
  },
};
</script>

<template>
  <div v-for="task in tasks">
    <Task
      :task="task"
      :changeCheckbox="changeCheckbox"
      :deleteTask="deleteTask"
    />
  </div>
</template>

<style scoped></style>
