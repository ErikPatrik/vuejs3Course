<template>
  <p>{{ company }} é lega</p>

  <!-- Com o exemplo abaixo ocorre erro, pois somente com a interpolação
        é possível adicionar mais texto -->
  <p v-text="company">é legal</p>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      company: 'Google'
    }
  }
})
</script>
