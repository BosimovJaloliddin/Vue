<template>
  <div class="filter-btns">
    <button
      @click="getCategory('all')"
      class="filter-btn b-left"
      :class="[category === 'all' ? 'active' : 'filter-btn']"
    >
      Barcha kinolar
    </button>
    <button
      @click="getCategory('like')"
      class="filter-btn"
      :class="[category === 'like' ? 'active' : 'filter-btn']"
    >
      Mashxur kinolar
    </button>
    <button
      @click="getCategory('popular')"
      class="filter-btn b-right"
      :class="[category === 'popular' ? 'active' : 'filter-btn']"
    >
      Eng ko'p ko'rilgan kinolar
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      category: this.pushCategoryName,
    };
  },
  props: {
    categoryName: {
      type: Function,
      required: true,
    },
    pushCategoryName: {
      type: String,
      required: true,
    },
  },
  methods: {
    getCategory(value) {
      this.categoryName(value);
      this.category = value;
    },
  },
};
</script>

<style scoped>
.filte-btns {
  display: flex;
  justify-content: flex-start;
  background-color: red;
}
.filter-btn {
  min-width: 80px;
  height: 36px;
  font-size: 1rem;
  font-weight: 550;
  padding: 7px 12px;
  background-color: #ffffff;
  color: #222222;
  cursor: pointer;
  transition: all 0.3s ease;
}
.b-left {
  border-top-left-radius: 7px;
  border-bottom-left-radius: 7px;
}
.b-right {
  border-top-right-radius: 7px;
  border-bottom-right-radius: 7px;
}
.active {
  color: #ffffff;
  background-color: #222222;
}
.filter-btn:hover {
  color: #ffffff;
  background-color: #222222;
}
</style>
