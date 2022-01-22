<template>
  <section>
    <h1>{{ infoData.title }}</h1>
    <p>{{ infoData.description }}</p>
  </section>
</template>

<script>
export default {
  name: "Info",
  props: {
    infoData: {
      title: String,
      description: String,
    },
  },
};
</script>

<style></style>
