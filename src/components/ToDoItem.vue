<template>
    <div>
        <b-list-group-item>
            <span v-if="todo.done" class="done">{{ todo.text }}</span>
            <span v-else>{{ todo.text }}</span>
            <b-button class="float-end" pill variant="outline-danger" @click="deleteTodo(todo)">&#10005;
            </b-button>
            <span v-if="todo.done" class="float-end">&#128077;</span>
            <b-button v-else class="float-end" pill variant="outline-success" @click="completeTodo(todo)">&#10003;
            </b-button>
        </b-list-group-item>
    </div>
</template>

<script>
    export default {
        name: "ToDoItem",
        props: {
            todo: {
                type: Object,
                required: true
            }
        },
        methods: {
            completeTodo(todo) {
                this.$emit("complete-todo", todo);
            },
            deleteTodo(todo) {
                this.$emit("delete-todo", todo);
            }
        }
    }
</script>

<style scoped>
    .done {
        text-decoration: line-through;
    }
    .list-group-item {
        padding-block: 15px;
    }
    .button {
        align-content: inherit;
        padding: 10px;
    }
    
</style>