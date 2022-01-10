<!--
    v-show: a tag é renderizada, mas mostra o display none
-->
<template>
  <div>
    <h1 v-show="sex === 'Masculino'">Masculino</h1>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      sex: 'Outro'
    }
  }
})
</script>
