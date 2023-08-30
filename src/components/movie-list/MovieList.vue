<template>
  <ul class="content">
    <MovieListItem v-for="movie in movies" v-bind:films="movie" />
  </ul>
</template>

<script>
import MovieListItem from "../movie-list-item/MovieListItem.vue";

export default {
  components: {
    MovieListItem,
  },
  data() {
    return {
      movies: [
        { id: 1, seen: 780, like: false, name: "Umar" },
        { id: 2, seen: 780, like: true, name: "Usmon" },
        { id: 3, seen: 780, like: false, name: "Halil" },
        { id: 4, seen: 780, like: true, name: "Ali" },
      ],
    };
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin-bottom: 60px;
}
</style>
