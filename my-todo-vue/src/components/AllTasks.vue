<script lang="ts">
import Task from "./Task.vue";
export default {
  name: "AllTasks",
  props: ["tasks", "changeCheckbox", "deleteTask", "selectValue"],

  components: {
    Task,
  },
};
</script>

<template>
  <div v-for="task in tasks" :key="task.id">
    <div v-if="selectValue === 'ALL'">
      <Task
        :task="task"
        :changeCheckbox="changeCheckbox"
        :deleteTask="deleteTask"
      />
    </div>
    <div v-if="selectValue === 'ActiveAll' && !task.checkbox">
      <Task
        :task="task"
        :changeCheckbox="changeCheckbox"
        :deleteTask="deleteTask"
      />
    </div>

    <div v-if="selectValue === 'UnActiveAll' && task.checkbox">
      <Task
        :task="task"
        :changeCheckbox="changeCheckbox"
        :deleteTask="deleteTask"
      />
    </div>
  </div>
</template>

<style scoped></style>
