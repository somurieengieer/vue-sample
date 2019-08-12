<template>
  <li>
    {{todo.taskName}}
  </li>
</template>

<script>
  export default {
    name: "TaskItem",
    props: {
      todo: {
        type: Object,
        required: true
      }
    }
  }
</script>

<style scoped>

</style>
