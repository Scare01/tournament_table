<template>
  <ul class="list">
    <li
      v-for="player in players"
      :key="player"
    >
      {{ player }}
    </li>
  </ul>
</template>

<script>
  export default {
    name: 'ListPlayers',
    props: {
      players: {
        type: Array,
        default: () => {
          return [];
        },
      },
    },
  }
</script>

<style scoped>
  .list {
    list-style-type: none;
  }
  .list > li {
    font-size: 20px;
  }
</style>
