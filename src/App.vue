<template>
  <div id="app">
    <InputComponent
      :bracket-size="brackerSize"
      @change-bracket-size="changeBracketSize"
    />
    <PlayersList :players="getPlayers()" />
    <Table
      :key="tableKey"
      :bracket-size="brackerSize"
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
    }
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
