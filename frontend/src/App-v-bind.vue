<template>
  <a :href="product.url" v-bind:class="productClass">
    {{ product.name }}
  </a>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      product: {
        name: 'Camisa',
        url: 'http://google.com/',
        stock: false
      }
    }
  },
  computed: {
    productClass(): string {
      return this.product.stock ? 'success' : 'danger'
    }
  }
})
</script>

<style>
.danger {
  color: red;
}

.success {
  color: green;
}
</style>
