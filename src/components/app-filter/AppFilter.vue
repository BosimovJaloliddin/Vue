<template>
  <div class="filter-btns">
    <button
      v-for="btn in btnCategory"
      :key="btn.id"
      @click="getCategory(btn.status)"
      class="filter-btn"
      :class="[category === btn.status ? 'active' : 'filter-btn']"
    >
      {{ btn.title }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      btnCategory: [
        { id: 1, title: "Barcha kinolar", status: "all" },
        { id: 2, title: "Mashxur kinolar", status: "like" },
        { id: 3, title: "Eng ko'p ko'rilgan kinolar", status: "popular" },
      ],
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
