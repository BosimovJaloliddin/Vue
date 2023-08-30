<template>
  <div class="content">
    <h2>Barcha kinolar soni: {{ allFilms }}</h2>
    <h3>Sevimli film: {{ likeFilms }}</h3>
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
  props: {
    allFilms: {
      type: Number,
      required: true,
    },
    likeFilms: {
      type: Number,
      required: true,
    },
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
