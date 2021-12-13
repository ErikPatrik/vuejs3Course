<template>
    <h1>{{ message }}</h1>
</template>

<script lang="ts">
import {defineComponent} from 'vue'

export default defineComponent({
    data() {
        return {
            message: 'Olá'
        }
    },
    beforeCreate() {
        // usamos quando precisamos fazer algo possível
        // mas que nao tenha contato com a DOM
        console.log(this.message) //undefined
    },
    created() {
        console.log(this.message)
    },
    // beforeMount e mounted tem acessos ao dados da Data
    // antes de montar o HTML/DOM, ele nao tem acesso a DOM, não possui acesso ao $el
    beforeMount() {
        console.log(this.$el)
    },
    // Aqui possui acesso a DOM, então aqui é recomendado fazer alterações na DOM
    mounted() {
        this.$el.style.background = 'red'
    },
    // Aqui se refere a mudanças de dados do componente
    beforeUpdate() {
        console.log('Antes da atualização')
    },
    updated() {
        console.log('Depois da atualização')
    }
})
</script>