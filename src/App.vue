<template>
  <div>
    <b-container>
      <b-row>
        <b-col>
          <ToDoList />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
  import ToDoList from './components/ToDoList'

  export default {
    name: 'App',
    components: {
      ToDoList
    }
  }
</script>

<style>
</style>