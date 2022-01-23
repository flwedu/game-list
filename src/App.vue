<template>
  <div id="app">
    <img src="./assets/game.png" alt="joystick logo" />
    <Info v-bind:infoData="appData" />
    <game-list v-bind:games="gameList" />
    <!-- 
      Criando um componente de formulário e ouvindo seu evento "addNewGame"
      Também pode ser representado por @addNewGame="addNewGame"
     -->
    <game-form v-on:addNewGame="addNewGame" />
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
  methods: {
    addNewGame: function (game) {
      // This method add a game to list
      this.gameList.push({
        id: this.gameList.length + 1,
        ...game,
      });
    },
  },
  data: function () {
    return {
      appData: {
        title: "Videogames History List",
        description: "A list with videogames and the release date",
      },
      gameList: [
        { id: 1, name: "Mario Bros", year: 1983 },
        { id: 2, name: "Mario Bros 2", year: 1988 },
        { id: 3, name: "Mario Bros 3", year: 1988 },
      ],
    };
  },
};
</script>

<style>
#app {
  display: grid;
  justify-items: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: auto;
  width: 50%;
  color: #1c2731;
}
img {
  width: 3rem;
  height: 3rem;
}
</style>
