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
    <div class="addTaskContainer">
      <h1>Добавить задачу</h1>
      <div class="addTaskWrapper">
        <input
          @keyup.enter="$emit('addNewTask')"
          @input="$emit('update:modelValue', $event.target.value)"
          :value="modelValue"
          type="text"
          class="addTaskInput"
          placeholder="Добавить задачу"
        />
        <button @click="$emit('addNewTask')" class="addTaskButton">
          <span class="buttonText"> Добавить </span>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.addTaskContainer {
  display: flex;
  flex-direction: column;
  background-color: rgb(44, 136, 44);

  align-items: center;
}
h1 {
  color: white;
}
.addTaskWrapper {
  margin-top: 20px;
  margin-bottom: 20px;
}
.addTaskInput {
  text-align: center;
  background-color: #d1db3f;
  border: none;
  font-size: 15px;
  padding-top: 10px;
  padding-bottom: 10px;
}
.addTaskButton {
  padding-top: 10px;
  padding-bottom: 10px;
  background-color: #db973f;
}
.buttonText {
  font-size: 15px;
}
</style>
