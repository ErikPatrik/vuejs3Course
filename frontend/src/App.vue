<!--
    v-on escuta eventos para manipular a DOM
-->

<template>
  <a href="#interno" v-on:click="something">Link interno</a>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  methods: {
    something() {
      console.log('Olá')
    }
  }
})
</script>
