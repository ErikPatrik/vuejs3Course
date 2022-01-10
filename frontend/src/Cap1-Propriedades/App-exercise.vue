<!--
[X] Definir o dado `todos`
[X] Preencher os `todos` quando o componente é criado
[X] Exibir em tela apenas `todos` concluídos
[X] Ter um método para concluir os `todos`
[X] Mostrar um alerta quando todos os `todos` forem finalizados
-->

<template>
    <p v-for="todo in doneTodos" :key="todo.text">
        {{ todo.text }}
    </p>

    <button @click="checkAllTodos">Finalizar tarefas</button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

interface Todo {
    text: string
    done: boolean
}

export default defineComponent({
    data() {
        return {
            todos: [
                { text: 'Estudar Typescript', done: true },
                { text: 'Lavar os pratos', done: false },
                { text: 'Aprender Nuxt.js', done: true }
            ] as Todo[]
        }
    },
    computed: {
        doneTodos() : Todo[] {
            return this.todos.filter((todo) => todo.done) //em cada interação tem o todo e retorna o todo que foi concluído
        }
    },
    watch: {
        todos(newValue: Todo[]) { // novo valor é um array de Todos
            const isFinished = !newValue.some(({done}) => !done)

            if (isFinished) {
                alert('Todas as tarefas encerradas')
            }
        }
    },
    created() {
        this.todos = [
            { text: 'Estudar Typescript', done: true },
            { text: 'Lavar os pratos', done: false },
            { text: 'Aprender Nuxt.js', done: true }
        ]
    },
    methods: {
        checkAllTodos() {
            this.todos = this.todos.map(({text}) => {
                return {
                    text,
                    done: true
                }
            })
        }
    }
})
</script>