<script>
export default {
  name: "Header",
  props: ["counter"],
};
</script>

<template>
  <div>
    <header class="header">
      <div class="header_wrapper">
        <span class="header_span">Осталось выполнить</span>

        <span class="header_span2">{{ counter }}</span>
      </div>
    </header>
  </div>
</template>

<style scoped>
.header {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgb(102, 151, 2);
}
.header_wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.header_span {
  text-align: center;
  color: white;
  font-size: 25px;
  font-weight: bold;
  padding-top: 10px;
  padding-bottom: 10px;
}
.header_span2 {
  font-size: 30px;
  color: white;
  text-align: center;
  padding-bottom: 10px;
}
</style>
