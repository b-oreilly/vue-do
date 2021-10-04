<template>
    <div>
        <b-card header="TodoList" header-tag="header">
            <b-list-group>
                <ToDoItem v-for="item in list" :key="item.id" :todo="item" />
            </b-list-group>
            <template v-slot:footer>
                <input type="text" v-model="todo" v-on:keyup.enter="addNewTodo()" placeholder="Add a Todo" />
                <b-button class="float-end" variant="primary" @click="addNewTodo()">Add</b-button>
            </template>
        </b-card>
    </div>
</template>

<script>
    import ToDoItem from '@/components/ToDoItem'

    export default {
        name: 'ToDoList',
        components: {
            ToDoItem
        },
        data() {
            return {
                list: [{
                        id: 1,
                        text: "Clean the house",
                        done: true
                    },
                    {
                        id: 2,
                        text: "Walk the dog",
                        done: false
                    },
                    {
                        id: 3,
                        text: "Create todo app using Vue",
                        done: false
                    }
                ],
                todoText: ""
            }
        },
        methods: {
            addNewTodo() {
                if (!this.todo) {
                    alert("Please enter some text.");
                    return;
                }

                // Getting the max ID in the list and adding 1 to it.
                const newId = Math.max.apply(null, this.list.map(t => t.id)) + 1;
                // Adding a todo to the list with a new id, the text entered in the input field and setting done to false.

                this.list.push({
                    id: newId,
                    text: this.todo,
                    done: false
                });

                // Reset todo to an empty string.
                this.todo = "";
            }
        }
    }
</script>

<style>
    .container {
        margin-top: 30px;
    }
</style>