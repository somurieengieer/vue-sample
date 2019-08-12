<template>
  <li>
    {{todo.taskName}}
    <button @click="$emit('remove', todo.id)">x</button>
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
