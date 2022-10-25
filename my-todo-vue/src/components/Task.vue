<script lang="ts">
export default {
  name: "Task",
  emits: ["changeCheckbox"],
  props: ["task", "changeCheckbox", "deleteTask"],
  setup() {
    return {};
  },
};
</script>

<template>
  <div>
    <div
      class="taskContainer"
      :class="task.checkbox ? 'taskContainerColor' : ''"
    >
      <span class="taskText" :class="task.checkbox ? 'taskTextDecoration' : ''">
        {{ task.taskText }}
      </span>
      <div>
        <input
          type="checkbox"
          @click="changeCheckbox(task.id)"
          :checked="task.checkbox"
        />
        <button @click="deleteTask(task.id)" class="buttonText">удалить</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.taskContainer {
  background-color: aliceblue;
  display: flex;
  justify-content: space-between;
  padding-top: 10px;
  padding-bottom: 20px;
}

.taskText {
  width: 50%;
  word-wrap: break-word;
  font-size: 18px;
  color: black;
  margin-left: 20px;
}
.buttonText {
  margin-right: 20px;
}

.taskTextDecoration {
  text-decoration: line-through;
}
.taskContainerColor {
  background: rgb(253, 188, 186);
}
</style>
