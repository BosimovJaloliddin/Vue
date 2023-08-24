<template>
  <div class="content">
    <h2>Barcha kinolar soni: {{ count }}</h2>
    <h3>Sevimli film: {{ like }}</h3>
  </div>
</template>

<script>
import { listFilms } from "../../data/data.js";

export default {
  data() {
    return {
      count: listFilms.length,
      like: listFilms.filter((v) => v.like).length,
    };
  },
};
</script>

<style scoped>
.content {
  margin-bottom: 50px;
}
.content h2 {
  font-size: 32px;
  font-weight: 700;
  color: #222222;
  background-color: #fafcf5;
}
.content h3 {
  font-size: 28px;
  font-weight: 600;
  color: #222222;
  background-color: #fafcf5;
}
</style>
