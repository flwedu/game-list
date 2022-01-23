<template>
  <ol>
    <li v-for="game in games" :key="game.id">
      {{ game.name }}, released in {{ game.year }}
      <button @click="deleteItem(game.id)">x</button>
    </li>
  </ol>
</template>

<script>
export default {
  name: "game-list",
  props: {
    games: [],
  },
  methods: {
    deleteItem: function (id) {
      this.$emit("deleteItem", id);
      const indexToDelete = this.games.findIndex((game) => game.id === id);
      this.games.splice(indexToDelete, 1);
    },
  },
};
</script>

<style></style>
