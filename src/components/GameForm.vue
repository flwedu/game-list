<template>
  <form name="newGame" v-on:submit.prevent="add" autocomplete="off">
    <span>Add a new game data:</span>
    <input type="text" name="name" id="name" placeholder="name" required />
    <input type="text" name="year" id="year" placeholder="year" required />
    <input type="submit" value="Add" />
  </form>
</template>

<script>
export default {
  props: {
    name: String,
    year: Number,
  },
  methods: {
    add: function () {
      const form = document.forms.newGame;
      // Emitindo um evento "addNewGame", que será ouvido pelo parent (App)
      this.$emit("addNewGame", {
        name: form.name.value,
        year: form.year.value,
      });
    },
  },
};
</script>

<style>
form {
  width: 15rem;
  background: #f6e6e4;
  padding: 1rem;
  display: grid;
  justify-items: center;
}
input {
  margin: 0.15rem;
  padding: 0.15rem;
  border-radius: 5px;
  border: 0px solid transparent;
}
input[type="submit"] {
  width: 50%;
  background: #0bb48b;
  padding: 0.3rem 1rem;
  color: #ffff;
}
</style>
