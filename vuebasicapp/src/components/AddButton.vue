<template>
  <div>
    <form @submit="addToDo">
      <input type="text" v-model="title" name="title">
      <button type="submit">Submit</button>
    </form>
  </div>
</template>
<script>

    import { v4 as uuidv4 } from 'uuid';

    export default {
    name: 'AddButton',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addToDo(event){
            event.preventDefault();
        
            const newToDoObject = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }
            
            this.$emit("add-todo-event", newToDoObject);
            this.title= '';
        }
    }
}
</script>