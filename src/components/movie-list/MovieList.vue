<template>
  <ul class="content">
    <MovieListItem />
    <MovieListItem />
    <MovieListItem />
  </ul>
</template>

<script>
import MovieListItem from "../movie-list-item/MovieListItem.vue";
import { listFilms } from "../../data/data";

export default {
  components: {
    MovieListItem,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin-bottom: 60px;
}
</style>
