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
          /* 新しい値で独自のinputイベントを創出する */
          // input: this.$emit('input', 'hoge') // このように書いたら'hoge'に書き換わって送出される
          input: event => this.$emit('input', event.target.value)
        }
      }
    }
  }
</script>

<style scoped>

</style>
