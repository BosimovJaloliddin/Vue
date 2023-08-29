<template>
  <li class="movie-list">
    <span class="movie-name">Usman</span>
    <span class="movie-seen">1200</span>
    <div class="list-icons">
      <button type="button" class="list-icon icon-cookie">
        <i class="fas fa-cookie"></i>
      </button>

      <button type="button" class="list-icon icon-trash">
        <i class="fas fa-trash"></i>
      </button>

      <button type="button" class="list-icon icon-stat">
        <i class="fas fa-star"></i>
      </button>
    </div>
  </li>
</template>

<script>
export default {};
</script>

<style scoped>
.movie-list {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 8px;
  border-bottom: 1px solid rgba(142, 141, 141, 0.56);
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
}
.movie-list:last-child {
  border-bottom: none;
}
</style>
