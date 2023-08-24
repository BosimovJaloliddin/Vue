<template>
  <div class="app">
    <div class="container">
      <AppInfo />
      <div class="search-panel content">
        <SearchPanel />
        <AppFilter />
      </div>
      <MovieList />
      <MovieAddForm />
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
