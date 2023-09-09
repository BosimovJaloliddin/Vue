<template>
  <div class="app">
    <div class="container">
      <AppInfo
        v-bind:allFilms="movies.length"
        v-bind:likeFilms="movies.filter((v) => v.like).length"
      />
      <div class="search-panel content">
        <SearchPanel :getValue="searchFilm" />
        <AppFilter
          :categoryName="getCategoryName"
          :pushCategoryName="category"
        />
      </div>
      <MovieList
        v-bind:films="
          filterCategory(searchListFilms(movies, searchVal), category)
        "
        @getId="getId"
        @onDel="removeItem"
      />
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
        { id: 1, seen: 780, favourite: true, like: false, name: "Umar" },
        { id: 2, seen: 580, favourite: false, like: true, name: "Usmon" },
        { id: 3, seen: 280, favourite: true, like: false, name: "Halil" },
        { id: 4, seen: 780, favourite: false, like: true, name: "Ali" },
        { id: 5, seen: 380, favourite: false, like: true, name: "Yulduz" },
        { id: 6, seen: 180, favourite: false, like: false, name: "Mira" },
        { id: 7, seen: 1800, favourite: false, like: true, name: "Ali" },
      ],
      searchVal: "",
      category: "all",
    };
  },
  methods: {
    newFilm(item) {
      (item?.name || item?.seen) && this.movies.push(item);
    },

    getId({ id, prop }) {
      this.movies = this.movies.map((v) => {
        if (v.id === id) return { ...v, [prop]: !v[prop] };
        else return v;
      });
    },
    removeItem(id) {
      this.movies = this.movies.filter((v) => v.id !== id);
    },

    // search filter
    searchListFilms(arr, v) {
      if (v.length === 0) return arr;

      return arr.filter((val) => val.name.toLowerCase().includes(v));
    },
    searchFilm(value) {
      this.searchVal = value.toLowerCase();
    },

    // category filter
    filterCategory(arr, category) {
      switch (category) {
        case "all":
          return arr;
        case "popular":
          return arr.filter((v) => v.seen >= 500);
        case "like":
          return arr.filter((v) => v.like);
      }
    },
    getCategoryName(value) {
      this.category = value;
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
