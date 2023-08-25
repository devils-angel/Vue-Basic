// ToDos.vue
<template>
    <div>
        <h1>TO DO LIST</h1>
        <ul>
          <li v-bind:key="item.id" v-for="item in todoEntries">
              <ToDoItem v-bind:todoItem="item" @set-completed=changeStatus />
          </li>   
      </ul>
    </div>
</template>


<script>
import ToDoItem from "./ToDoItem";

export default {
  name: 'ToDos',
  components: {
      ToDoItem
  },
  props: [
      "todoEntries"
  ],
  methods: {
    changeStatus() {
      this.todoItem.completed= true;
    }
  },
}
</script>