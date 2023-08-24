<template>
  <div class="filter-btns">
    <button class="filter-btn b-left active">Barcha kinolar</button>
    <button class="filter-btn">Mashxur kinolar</button>
    <button class="filter-btn b-right">Eng ko'p ko'rilgan kinolar</button>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.filte-btns {
  display: flex;
  justify-content: flex-start;
  background-color: red;
}
.filter-btn {
  min-width: 80px;
  height: 36px;
  font-size: 1rem;
  font-weight: 550;
  padding: 7px 12px;
  background-color: #ffffff;
  color: #222222;
  cursor: pointer;
  transition: all 0.3s ease;
}
.b-left {
  border-top-left-radius: 7px;
  border-bottom-left-radius: 7px;
}
.b-right {
  border-top-right-radius: 7px;
  border-bottom-right-radius: 7px;
}
.active {
  color: #ffffff;
  background-color: #222222;
}
.filter-btn:hover {
  color: #ffffff;
  background-color: #222222;
}
</style>
