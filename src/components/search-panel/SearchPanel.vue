<template>
  <div class="wrapper">
    <input v-on:input="onChange" type="text" placeholder="Search film" />
  </div>
</template>

<script>
export default {
  props: {
    getValue: {
      type: Function,
      required: true,
    },
  },
  methods: {
    onChange(e) {
      this.getValue(e.target.value);
    },
  },
};
</script>

<style scoped>
.wrapper {
  margin-bottom: 20px;
}
.wrapper input {
  display: block;
  width: 100%;
  height: 48px;
  border: 1px solid rgb(213, 213, 247);
  border-radius: 7px;
  padding: 4px 12px;
  outline: none;
}
.wrapper input:hover {
  box-shadow: 0 0 3px #888888;
}
</style>
