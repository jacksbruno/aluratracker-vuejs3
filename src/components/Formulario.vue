<template lang="pug">
.box
  .columns
    .column.is-8
      input(
        type="text"
        class="input"
        placeholder="Qual tarefa você deseja iniciar?"
        v-model="descricao"
      )
    Temporizador(@temporizadorFinalizado="finalizarTarefa")
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Temporizador from './Temporizador.vue'

export default defineComponent({
  name: 'Formulario',

  components: {
    Temporizador
  },

  data: () => ({
    descricao: ''
  }),

  methods: {

    finalizarTarefa(tempo: number) : void{
      const dados = {
        tempo: tempo,
        descricaoTarefa: this.descricao
      }
      this.$emit('temporizadorFinalizado', dados)
      this.descricao = ''
    }
  }
})
</script>