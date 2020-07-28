<template>
  <ul>
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
