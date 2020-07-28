<template>
  <div id="app">
    <InputComponent
      :bracket-size="brackerSize"
      @change-bracket-size="changeBracketSize"
    />
    <div>
      <PlayersList :players="getPlayers()" />
      <button
        @click="fillTable"
      >fill table</button>
    </div>
    <Table
      :key="tableKey"
      :bracket-size="brackerSize"
      :players="playerForTable"
    />
  </div>
</template>

<script>
import Table from './components/table';
import InputComponent from './components/input';
import PlayersList from './components/list-players';

export default {
  name: 'App',
  components: {
    Table,
    InputComponent,
    PlayersList,
  },
  data() {
    return {
      brackerSize: 8,
      tableKey: 0,
      playerForTable: [],
    };
  },
  methods: {
    changeBracketSize(brackerSize) {
      this.brackerSize = Number(brackerSize, 10);
      this.tableKey += 1;
    },
    getPlayers() {
      let players = [];

      for (let i = 1; i <= this.brackerSize; i++) {
        players.push(`player${i}`);
      }
      console.log(players);
      return players;
    },
    fillTable() {
      this.playerForTable = this.getPlayers().sort(() => Math.random() - 0.5);
    },
  },
}
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
