<template>
    <h1>{{ person.name }} {{ person.lastname }}</h1>
    <h1>{{ fullName }}</h1>
</template>

<script lang="ts">
import { defineComponent } from "vue";

interface Person {
    name: string
    lastname: string
}

export default defineComponent({
    data() {
        return {
            person: {
                name: 'Erik',
                lastname: 'Pittaluga'
            } as Person
        }
    },
    //retorna algum dado com algum tipo de alteração
    computed: {
        fullName(): string {
            return `${this.person.name} ${this.person.lastname}`
        }
    }
})
</script>