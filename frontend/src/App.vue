<template>
  <p>{{ count }}</p>
  <button @click="increment"></button>
</template>

<script lang="ts" setup>
import { ref, watch } from 'vue'

function useCount(n = 0) {
  const count = ref(n)

  function increment() {
    return count.value++
  }

  return {
    count,
    increment
  }
}

const { count, increment } = useCount()
const a = ref('name')

watch([count, a], ([value, novoA], [oldValue, antigoA]) => {
  console.log(oldValue, value)
})
</script>
