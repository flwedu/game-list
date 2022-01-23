<template>
  <li>
    {{ game.name }}, released in {{ game.year }}
    <button @click="deleteItem(game.id)">x</button>
  </li>
</template>

<script>
export default {
  name: "game-list",
  props: {
    game: {
      id: Number,
      name: String,
      year: Number,
    },
  },
  methods: {
    deleteItem: function (id) {
      this.$emit("deleteItem", id);
    },
  },
};
</script>

<style></style>
