<script>
import { ref } from "vue";
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
    const counter = ref(0);
    const addNewTask = () => {
      counter.value += 1;
    };
    return {
      counter,
      addNewTask,
    };
  },
};
</script>

<template>
  <Header :counter="counter" />
  <MainMenu />
  <Filter />
  <AllTasks />
</template>

<style scoped></style>
