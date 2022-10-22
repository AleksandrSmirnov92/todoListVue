<script setup lang="ts"></script>

<template>
  <div>
    <div class="filter_block">
      <select class="filter">
        <option>Выбрать все</option>
        <option>Выбрать активные</option>
        <option>Выбрать законченные</option>
      </select>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

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
