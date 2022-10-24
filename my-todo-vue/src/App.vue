<script lang="ts">
import { ref, reactive } from "vue";
import Header from "./components/Header.vue";
import MainMenu from "./components/MainMenu.vue";
import Filter from "./components/Filter.vue";
import AllTasks from "./components/AllTasks.vue";

export default {
  name: "App",
  components: {
    Header,
    MainMenu,
    Filter,
    AllTasks,
  },
  setup() {
    const state = reactive({
      tasks: [
        {
          id: 5,
          taskText: "привет!",
          checkbox: false,
        },
        {
          id: Math.random(),
          taskText: "как дела?",
          checkbox: false,
        },
      ],
      counter: 0,
      selectValue: "",
    });
    const inputText = ref("");

    const addNewTask = () => {
      if (!inputText.value.trim()) {
        alert("Вы ничего не ввели!");
      } else {
        state.tasks.push({
          id: Math.random(),
          taskText: inputText.value,
          checkbox: false,
        });
        state.counter += 1;
        inputText.value = "";
      }
    };
    const deleteTask = (id: number) => {
      if (!state.tasks.find((item) => item.id === id)!.checkbox) {
        state.counter -= 1;
      }
      state.tasks = state.tasks.filter((item) => item.id !== id);
    };

    const changeCheckbox = (id: number): void => {
      state.tasks.find((item) => item.id === id)!.checkbox = !state.tasks.find(
        (item) => item.id === id
      )!.checkbox;
      if (!state.tasks.find((item) => item.id === id)!.checkbox) {
        state.counter += 1;
      } else {
        state.counter -= 1;
      }
    };
    return {
      state,
      addNewTask,
      changeCheckbox,
      deleteTask,
      inputText,
    };
  },
};
</script>

<template>
  <Header :counter="state.counter" />
  <MainMenu @addNewTask="addNewTask()" v-model.trim.lazy="inputText" />
  <Filter v-model="state.selectValue" />
  <AllTasks
    :tasks="state.tasks"
    :changeCheckbox="changeCheckbox"
    :deleteTask="deleteTask"
  />
</template>

<style scoped></style>
