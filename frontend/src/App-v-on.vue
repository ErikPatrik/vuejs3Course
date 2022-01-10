<!--
    // prevent // previne o comportamento padrão
    // once // acontece apenas uma vez
    // prevent.once // previne e acontece apenas uma vez
-->

<template>
  <a href="#interno" v-on:click.prevent="something">Link interno</a>
  <a href="#interno" @click.prevent="something">Link interno</a>
  <input type="text" @keyup="something" />
  <input type="text" @keyup.k="something" />
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
