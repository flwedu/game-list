<template>
  <form name="newGame" v-on:submit.prevent="add" autocomplete="off">
    <input
      type="text"
      v-model="name"
      name="name"
      id="name"
      placeholder="name"
    />
    <input
      type="text"
      v-model="year"
      name="year"
      id="year"
      placeholder="year"
    />
    <button type="submit">Add</button>
  </form>
</template>

<script>
export default {
  props: {
    name: String,
    year: Number,
  },
  methods: {
    add: () => {
      console.log("button clicked");
    },
  },
};
</script>

<style></style>
