<script lang="ts">
import Task from "./Task.vue";
export default {
  name: "AllTasks",
  comments: {
    Task,
  },
  setup() {
    return {
      Task,
    };
  },
};
</script>

<template>
  <div>
    <Task />
  </div>
</template>

<style scoped></style>
