<template>
    <div>
        <b-card header="TodoList" header-tag="header">
            <template v-slot:footer>
                <b-button class="float-end" variant="primary">Add</b-button>
            </template>
        </b-card>
    </div>
</template>

<script>
    export default {
        name: 'ToDoList',
        components: {

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
                ]
            }
        }
    }
</script>

<style>
    .container {
        margin-top: 30px;
    }
</style>