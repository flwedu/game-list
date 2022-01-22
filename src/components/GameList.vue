<template>
  <li>{{ game.name }}, released in {{ game.year }}</li>
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
};
</script>

<style></style>
