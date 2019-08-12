<template>
  <input type="text"
         :value="taskName"
         v-on="listeners"
         />
</template>

<script>
  export default {
    name: "TaskNameText",
    props: {
      taskName: {
        type: String,
        default: ''
      }
    },
    computed: {
      listeners() {
        return {
          input: event => this.$emit('input', event.target.value)
        }
      }
    }
  }
</script>

<style scoped>

</style>
