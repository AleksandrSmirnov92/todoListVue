<script lang="ts">
export default {
  name: "MainManu",
  emits: ["addNewTask", "update:modelValue"],
  props: {
    modelValue: String,
  },
};
</script>

<template>
  <div>
    <div class="add_task">
      <h1 class="add_task_text">Добавить задачу</h1>
      <div class="add_task_input_and_button">
        <input
          @keyup.enter="$emit('addNewTask')"
          @input="$emit('update:modelValue', $event.target.value)"
          :value="modelValue"
          type="text"
          class="add_task_input"
          placeholder="Добавить задачу"
        />
        <button @click="$emit('addNewTask')" class="button_add">
          <span class="button_add_text"> Добавить </span>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.add_task {
  display: flex;
  flex-direction: column;
  background-color: rgb(44, 136, 44);

  align-items: center;
}
.add_task_text {
  color: white;
}
.add_task_input_and_button {
  margin-top: 20px;
  margin-bottom: 20px;
}
.add_task_input {
  text-align: center;
  background-color: #d1db3f;
  border: none;
  font-size: 15px;
  padding-top: 10px;
  padding-bottom: 10px;
}
.button_add {
  padding-top: 10px;
  padding-bottom: 10px;
  background-color: #db973f;
}
.button_add_text {
  font-size: 15px;
}
</style>
