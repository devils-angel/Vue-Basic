<template>
  <div id="app">
    <ToDos v-bind:todoEntries="todoEntries" />
    <AddButton @add-todo-event="addToDoItem"/>
  </div>
</template>

<style>

</style>

<script>
  import AddButton from './components/AddButton'
  import ToDos from './components/ToDos'
  
  export default {
  name: 'App',
  components: {
  ToDos,
  AddButton
  },
  data() {
      return {
          todoEntries: [
              ],
          }
      },
  methods: {
    addToDoItem(newToDoItem) {
      this.todoEntries = [...this.todoEntries, newToDoItem];
    }
  },
  }
</script>