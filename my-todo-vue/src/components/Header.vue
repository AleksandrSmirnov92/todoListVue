<script>
export default {
  name: "Header",
  props: ["counter"],
};
</script>

<template>
  <div>
    <header class="headerContainer">
      <div class="headerWrapper">
        <span class="headerSpanText">Осталось выполнить</span>

        <span class="headerSpanCounter">{{ counter }}</span>
      </div>
    </header>
  </div>
</template>

<style scoped>
.headerContainer {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgb(102, 151, 2);
}
.headerWrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.headerSpanText {
  text-align: center;
  color: white;
  font-size: 25px;
  font-weight: bold;
  padding-top: 10px;
  padding-bottom: 10px;
}
.headerSpanCounter {
  font-size: 30px;
  color: white;
  text-align: center;
  padding-bottom: 10px;
}
</style>
