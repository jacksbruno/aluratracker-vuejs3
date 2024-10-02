<template lang="pug">
  main(class="columns is-gapless is-multiline")
    .column.is-one-quarter
      BarraLateral
    .column.is-three-quarter
      router-view
      
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import BarraLateral from './components/BarraLateral.vue'

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
  },
})
</script>

<style lang="scss">
main{
  .column{
    .lista{
      padding: 1.25rem;
    }
  }
}
</style>
