<template>
    <h1>{{count}}</h1>
    <button @click="increment">Incrementar</button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    data() {
        return {
            count: 0
        }
    },
    methods: {
        increment() {
            this.count++
        }
    },
    watch: {
        // objeto que observa vários dados
        // passamos o nome da propriedade como função
        count(newValue, oldValue) {
            console.log(oldValue)
            console.log(newValue)
        }
    }
})
</script>