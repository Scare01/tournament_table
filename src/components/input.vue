<template>
  <div class="config">
      <strong>Количество игроков:</strong>
      <input
        type="text"
        :value="bracketSize"
        @change="$emit('change-bracket-size', $event.target.value)"
        placeholder="1, 2, 4, 8, 16, 32, 64, 128, 256">
    </div>
</template>

<script>
  export default {
    name: 'Input',
    props: {
      bracketSize: {
        type: Number,
        default: 8
      },
    },
    computed: {}
  }
</script>
