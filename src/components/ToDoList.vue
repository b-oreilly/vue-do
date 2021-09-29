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

        }
    }
</script>

<style scoped>

</style>