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
      class="add_task_result1"
      :class="task!.checkbox ? 'add_task_chacked_color' : ''"
    >
      <span
        class="add_task_result_text"
        :class="task!.checkbox ? 'add_task_result_text_t' : ''"
      >
        {{ task!.taskText }}
      </span>
      <div>
        <input
          type="checkbox"
          @click="changeCheckbox(task!.id)"
          :checked="task!.checkbox "
        />
        <button
          @click="deleteTask(task!.id)"
          class="add_task_result_text_remove"
        >
          удалить
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.add_task_result {
  background-color: aliceblue;
  display: flex;
  justify-content: space-between;
  padding-top: 10px;
  padding-bottom: 20px;
}
.add_task_result1 {
  background-color: aliceblue;
  display: flex;
  justify-content: space-between;
  padding-top: 10px;
  padding-bottom: 20px;
}
.add_task_result2 {
  background-color: aliceblue;
  display: none;
  justify-content: space-between;
  padding-top: 10px;
  padding-bottom: 20px;
}
.add_task_result_text {
  width: 50%;
  word-wrap: break-word;
  font-size: 18px;
  color: black;
  margin-left: 20px;
}
.add_task_result_text_remove {
  margin-right: 20px;
}

.add_task_result_text_t {
  text-decoration: line-through;
}
.add_task_chacked_color {
  background: rgb(253, 188, 186);
}
</style>
