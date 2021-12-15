<!--
Converter uma string em HTML
-->

<template>
  <p>
    Acesse:
    <span v-html="link"></span>
  </p>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      link: '<a href="http://google.com/">Google</a>'
    }
  }
})
</script>
