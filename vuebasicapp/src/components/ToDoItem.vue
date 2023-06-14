// ToDoItem.vue
<template>
  <div v-bind:class="{ 'completed' : todoItem.completed }">
    <p  v-on:click="markComplete(todoItem)">{{ todoItem.title }}</p>
  </div>
</template>

<script>

export default {
  name: 'ToDoItem',
  
  components: {
  },
  
  props: [
    "todoItem"
  ],
  
  methods: {
      markComplete(){
      this.$emit('set-completed', true)
    }
    }
  
}
</script>

<style>
      .completed {
        text-decoration: line-through;
      }
    </style>