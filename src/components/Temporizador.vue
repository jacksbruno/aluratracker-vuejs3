<template lang="pug">
.column
  .is-flex.is-align-items-center.is-justify-content-space-between
    Cronometro(:tempoEmSegundos="tempo")
    button.button(@click="iniciar" :disabled="cronometroAtivo")
      div Iniciar
      .icon
        i.fas.fa-play
    button.button(@click="finalizar" :disabled="!cronometroAtivo")
      div Finalizar
      .icon
        i.fas.fa-stop
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Cronometro from './Cronometro.vue'

export default defineComponent({
  name: 'Temporizador',

  components: {
    Cronometro
  },

  data: () => ({
    tempo: 0,
    cronometro: 0,
    cronometroAtivo: false
  }),

  methods: {
    iniciar() {
      this.cronometroAtivo = true
      this.cronometro = setInterval(() => {
        this.tempo += 1
      }, 1000)
    },
    finalizar() {
      this.cronometroAtivo = false
      clearInterval(this.cronometro)
      this.$emit('temporizadorFinalizado', this.tempo)
      this.tempo = 0
    }
  }
})

</script>

<style lang="scss">
.button {
  display: flex;
  align-items: center;
  justify-content: space-between;
  box-sizing: border-box;
}
</style>