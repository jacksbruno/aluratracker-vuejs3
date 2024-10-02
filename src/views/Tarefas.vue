<template lang="pug">
  Formulario(@temporizadorFinalizado="inserirTarefa")
  .lista
    Tarefa(v-for="(tarefa, i) in tarefas" :tarefa="tarefa" :key="i")
    Box(v-if="!tarefas.length") Você não está muito produtivo hoje :(
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ITarefa from '@/interfaces/ITarefa'
import Formulario from '@/components/Formulario.vue'
import Tarefa from '@/components/Tarefa.vue'
import Box from '@/components/Box.vue'

export default defineComponent({
  name: 'App',
  components: {
    Formulario,
    Tarefa,
    Box
  },

  data: () => ({
    tarefas: [] as ITarefa[],
  }),

  methods: {
    inserirTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    }
  }
})
</script>