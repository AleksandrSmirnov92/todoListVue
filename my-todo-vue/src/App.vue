<script lang="ts">
import { ref, reactive, onMounted, onUpdated } from "vue";
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
    const inputText = ref("");
    interface STATE {
      tasks: {
        id: number;
        taskText: string;
        checkbox: boolean;
      }[];
      counter: number;
      selectValue: string;
    }
    let state: STATE = reactive({
      tasks: [],
      counter: 0,
      selectValue: "ALL",
    });
    onMounted(() => {
      if (localStorage.getItem("tasks")) {
        state.tasks = JSON.parse(localStorage.getItem("tasks")!);
      }
      if (localStorage.getItem("counter")) {
        state.counter = JSON.parse(localStorage.getItem("counter")!);
      }
    });
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
    const deleteTask = (id: number): void => {
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

    onUpdated(() => {
      localStorage.setItem("tasks", JSON.stringify(state.tasks));
      localStorage.setItem("counter", JSON.stringify(state.counter));
    });
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
    :selectValue="state.selectValue"
  />
</template>

<style scoped></style>
