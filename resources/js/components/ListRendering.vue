<template>
    <div class="list-rendering">
        <ul>
            <li v-for="todo in listCompleteTodo" :key = "todo.id">
                {{ todo.name }} - {{ todo.isComplete }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                todos: [
                    {
                        id : 1,
                        name: 'to do 1',
                        isComplete: true
                    },
                    {
                        id: 2,
                        name: 'to do 2',
                        isComplete: false
                    },
                    {
                        id: 3,
                        name: 'to do 3',
                        isComplete: true
                    },
                ]
            }
        },
        computed: {
            listCompleteTodo() {
                return this.todos.filter(item => item.isComplete)
            }
        }
    }
</script>

<style lang="scss" scoped>
</style>