<template>
  <li class="movie-list" v-bind:class="[{ like: films.like }]">
    <span class="movie-name">{{ films.name }}</span>
    <span class="movie-seen">{{ films.seen }}</span>
    <div class="list-icons">
      <button
        type="button"
        class="list-icon icon-cookie"
        v-bind:class="[{ like: true }]"
      >
        <i class="fas fa-cookie"></i>
      </button>

      <button type="button" class="list-icon icon-trash">
        <i class="fas fa-trash"></i>
      </button>

      <button type="button" class="list-icon icon-star">
        <i class="fas fa-star"></i>
      </button>
    </div>
  </li>
</template>

<script>
// document.querySelector(".icon-cookie").classList.toggle("like");

export default {
  props: {
    films: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.movie-list {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 8px;
  border-bottom: 1px solid rgba(142, 141, 141, 0.56);
  cursor: pointer;
}
.movie-list .movie-name {
  display: inline-block;
  flex: 0 0 75%;
  max-width: 75%;
  font-size: 24px;
  font-weight: 600;
  color: #222222;
}
.movie-list .movie-seen {
  display: inline-block;
  flex: 0 0 10%;
  max-width: 10%;
  font-size: 22px;
  font-weight: 800;
  color: coral;
}
.movie-list .list-icons {
  display: inline-block;
  flex: 0 0 15%;
  max-width: 15%;
  display: flex;
  justify-content: space-between;
}
.list-icons button {
  width: 40px;
  height: 40px;
  margin-left: 8px;
  cursor: pointer;
  background-color: #ffffff;
  border: 0;
  border-radius: 50%;
}
.list-icons button i {
  font-size: 18px;
}
.list-icons button:active {
  transform: scale(0.94);
}
.list-icons .icon-cookie {
  color: #e09f3e;
}
.list-icons .icon-trash {
  color: rgb(231, 66, 66);
}
.list-icons .icon-star {
  color: rgb(225, 218, 10);
  transform: translateX(30px);
  opacity: 0;
}
.movie-list.like .icon-star {
  opacity: 1;
  transform: translateX(0px);
}
.movie-list.like .movie-name {
  color: #e09f3e;
}
.movie-list:last-child {
  border-bottom: none;
}
</style>
