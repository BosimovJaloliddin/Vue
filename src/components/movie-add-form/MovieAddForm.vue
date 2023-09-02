<template>
  <div class="content">
    <h3>Add new film</h3>
    <form action="#" class="add-form" @submit.prevent>
      <input
        @change="name = $event.target.value"
        v-bind:value="name"
        class="name-film form-input"
        type="text"
        placeholder="Film nomi"
      />
      <input
        @change="number = $event.target.value"
        v-bind:value="number"
        class="count-film form-input"
        type="number"
        placeholder="Necha marta ko'tilgan"
      />
      <button class="add-btn" type="submit" @click="getForm">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      number: 0,
    };
  },
  methods: {
    getForm() {
      const formInfo = {
        name: this.name,
        seen: this.number,
        like: false,
        id: Date.now(),
      };
      this.name = "";
      this.number = 0;
      this.$emit("creatFilm", formInfo);
    },
  },
};
</script>

<style scoped>
h3 {
  font-size: 24px;
  font-weight: 600;
  color: #222222;
  margin-bottom: 20px;
}
.add-form {
  display: flex;
  gap: 2%;
}
.name-film {
  flex: 0 0 60%;
  max-width: 60%;
}
.count-film {
  flex: 0 0 20%;
  max-width: 20%;
}
.form-input {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 38px;
  padding: 7px 12px;
  border: 1px solid #888888;
  border-radius: 5px;
  outline: none;
}
.add-btn {
  flex: 0 0 16%;
  max-width: 16%;
  font-size: 22px;
  font-weight: 500;
  color: #ffffff;
  background-color: rgb(24, 24, 136);
  border: 0;
  border-radius: 5px;
  cursor: pointer;
}
.form-input:hover {
  box-shadow: 0 0 7px #888888;
}
.add-btn:active {
  transform: scale(0.96);
}
</style>
