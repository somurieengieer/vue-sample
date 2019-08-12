<template>
  <div>
    <div>Test Task List page.</div>
    <TaskNameText v-model="newTaskName"
    />
    <button v-on:click="addTodo">Add Task</button>
    <ul v-if="todos.length">
      <TaskItem v-for="todo in todos"
                :key="todo.id"
                :todo="todo"
                @remove="removeTodo"
                />
    </ul>
  </div>
</template>

<script>
  import TaskItem from "@/components/TaskItem";
  import TaskNameText from "@/components/TaskNameText";
  let Todo = function (id, name) {
    this.id = id;
    this.taskName = name;
    this.done = false;
  }

  let idCounter = 0

  export default {
    name: 'Tasks',
    components: {TaskNameText, TaskItem},
    data() {
      return {
        newTaskName: '',
        todos: []
      }
    },
    methods: {
      addTodo: function () {
        const newTaskName = this.newTaskName.trim()
        if (newTaskName) {
          this.todos.push(new Todo(idCounter++, newTaskName))
        }
      },
      removeTodo(idToRemove) {
        this.todos = this.todos.filter(todo => {
          return todo.id !== idToRemove
        })
      }
    }
  }
</script>

<style scoped>

</style>
