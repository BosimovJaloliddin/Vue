<template>
  <ul class="content">
    <MovieListItem v-for="movie in films" v-bind:film="movie" />
  </ul>
</template>

<script>
import MovieListItem from "../movie-list-item/MovieListItem.vue";

export default {
  components: {
    MovieListItem,
  },
  props: {
    films: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin-bottom: 60px;
}
</style>
