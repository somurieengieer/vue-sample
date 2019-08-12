<template>
  <input type="text"
         :value="value"
         v-on="listeners"
         />
</template>

<script>
  export default {
    name: "TaskNameText",
    props: {
      value: {
        type: String,
        default: ''
      }
    },
    computed: {
      listeners() {
        return {
          // Pass all component listeners directly to input
          ...this.$listeners,
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
