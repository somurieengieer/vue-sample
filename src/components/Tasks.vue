<template>
  <div>
    <div>Test Task List page.</div>
    <button v-on:click="addTodo">Add Task</button>
    <div v-for="todo in todos">
      <p>{{todo.taskName}}</p>
    </div>
  </div>
</template>

<script>
  var Todo = function (name) {
    this.taskName = name;
    this.done = false;
  }
  export default {
    name: 'Tasks',
    data() {
      return {
        todos: []
      }
    },
    methods: {
      addTodo: function () {
        this.todos.push(new Todo('Test'))
      }
    }
  }
</script>

<style scoped>

</style>
