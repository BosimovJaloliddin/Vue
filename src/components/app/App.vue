<template>
  <div class="app">
    <div class="container">
      <AppInfo
        v-bind:allFilms="movies.length"
        v-bind:likeFilms="movies.filter((v) => v.like).length"
      />
      <div class="search-panel content">
        <SearchPanel />
        <AppFilter />
      </div>
      <MovieList v-bind:films="movies" />
      <MovieAddForm @creatFilm="newFilm" />
    </div>
  </div>
</template>

<script>
import AppInfo from "../app-info/AppInfo.vue";
import SearchPanel from "../search-panel/SearchPanel.vue";
import MovieList from "../movie-list/MovieList.vue";
import MovieAddForm from "../movie-add-form/MovieAddForm.vue";
import AppFilter from "../app-filter/AppFilter.vue";

export default {
  components: {
    AppInfo,
    SearchPanel,
    MovieList,
    MovieAddForm,
    AppFilter,
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
  methods: {
    newFilm(item) {
      (item?.name || item?.seen) && this.movies.push(item);
    },
  },
};
</script>

<style>
.app {
  width: 100vw;
  margin-bottom: 50px;
}
.container {
  max-width: 1000px;
  margin: 40px auto;
  background-color: #ffffff;
  padding: 0 15px;
}
</style>
