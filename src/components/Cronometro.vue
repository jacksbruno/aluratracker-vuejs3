<template lang="pug">
section
  strong(:style="{ color }") {{ tempoDecorrido }}
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Cronometro',

  props: {
    tempoEmSegundos: {
      type: Number,
      default: 0
    },
    color: {
      type: String,
      default: '#000'
    }
  },

  computed: {
    tempoDecorrido() : string {
      return new Date(this.tempoEmSegundos * 1000).toISOString().substring(11, 19)
    }
  },
})

</script>