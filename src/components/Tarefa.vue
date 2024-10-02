<template lang="pug">
Box
  .columns
    .column.is-7 {{ tarefa.descricaoTarefa || 'Tarefa sem descrição' }}
    .column
      Cronometro(:tempoEmSegundos="tarefa.tempo" color="#fff")
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Box from './Box.vue'
import Cronometro from './Cronometro.vue'
import ITarefa from '../interfaces/ITarefa'

export default defineComponent({
  name: 'Tarefa',
  components: {
    Box,
    Cronometro
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      require: true
    }
  }
})
</script>
