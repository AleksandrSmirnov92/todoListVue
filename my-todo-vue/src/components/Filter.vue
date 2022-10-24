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
    <div class="filter_block">
      <select
        class="filter"
        @change="$emit('update:modelValue', $event.target.value)"
      >
        <option value="ALL" default>Выбрать все</option>
        <option value="ActiveAll">Выбрать активные</option>
        <option value="UnActiveAll">Выбрать законченные</option>
      </select>
    </div>
  </div>
</template>

<style scoped>
.filter_block {
  background: #d1db3f;
  display: flex;
  justify-content: center;
  padding-top: 25px;
  padding-bottom: 10px;
}
.filter {
  background-color: #db973f;

  font-size: 18px;
}
</style>
