<template lang="pug">
.box.has-text-weight-bold
  slot
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Box'
})
</script>

<style lang="scss" scoped>
.box{
  background: #35495e;
  color: #fff;
}
</style>