<template>
  <div class="wrapper">
    <input type="text" placeholder="Search film" />
    <div></div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.wrapper {
  margin-bottom: 20px;
}
.wrapper input {
  display: block;
  width: 100%;
  height: 48px;
  border: 1px solid rgb(213, 213, 247);
  border-radius: 7px;
  padding: 4px 12px;
  outline: none;
}
.wrapper input:hover {
  box-shadow: 0 0 3px #888888;
}
</style>
