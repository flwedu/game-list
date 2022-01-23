<template>
  <ol>
    <li v-for="game in games" :key="game.id">
      "{{ game.name }}", released in {{ game.year }}
      <button @click="deleteItem(game.id)">x</button>
    </li>
  </ol>
</template>

<script>
export default {
  name: "game-list",
  props: {
    games: Array,
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

<style scoped>
button {
  color: #5f5f5f;
  background: transparent;
  border: transparent;
}
button:hover {
  font: bolder;
  color: red;
}
</style>
