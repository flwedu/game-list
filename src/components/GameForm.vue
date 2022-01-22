<template>
  <form name="newGame" autocomplete="off">
    <input type="text" name="name" id="name" placeholder="name" />
    <input type="text" name="year" id="year" placeholder="year" />
    <button type="button" v-on:click="add">Add</button>
  </form>
</template>

<script>
export default {
  methods: {
    add: () => {
      console.log("button clicked");
    },
  },
};
</script>

<style></style>
