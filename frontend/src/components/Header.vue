<template>
  <h1>
    {{ titulo }}
  </h1>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: ['titulo']
})
</script>
