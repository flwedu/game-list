<template>
  <div id="app">
    <img
      src="./assets/game.png"
      alt="an game logo"
      width="50px"
      height="50px"
    />
    <Info v-bind:infoData="appData" />
    <ol>
      <game-list
        v-for="elem in gameList"
        v-bind:key="elem.id"
        v-bind:game="elem"
      ></game-list>
    </ol>
    <game-form />
  </div>
</template>

<script>
import GameForm from "./components/GameForm.vue";
import GameList from "./components/GameList.vue";
import Info from "./components/Info.vue";

export default {
  name: "App",
  components: {
    Info,
    GameList,
    GameForm,
  },
  data: function () {
    return {
      appData: {
        title: "VideoGames history List",
        description: "A list with videogames and the release date",
      },
      gameList: [{ id: 1, name: "Mario Bros", year: 1985 }],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
