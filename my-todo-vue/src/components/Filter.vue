<script lang="ts">
export default {
  name: "Filter",
  emits: ["update:modelValue"],
  props: {
    modelValue: String,
  },
};
</script>

<template>
  <div>
    <div class="filterContainer">
      <select
        class="filterSelect"
        @change="$emit('update:modelValue', $event.target.value)"
      >
        <option value="ALL" selected>Выбрать все</option>
        <option value="ActiveAll">Выбрать активные</option>
        <option value="UnActiveAll">Выбрать законченные</option>
      </select>
    </div>
  </div>
</template>

<style scoped>
.filterContainer {
  background: #d1db3f;
  display: flex;
  justify-content: center;
  padding-top: 25px;
  padding-bottom: 10px;
}
.filterSelect {
  background-color: #db973f;
  font-size: 18px;
}
</style>
