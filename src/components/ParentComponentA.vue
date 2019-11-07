<template>
    <div style="border: 1px solid black">
        <h4>{{title}}</h4>
        <div>这个是父组件传进来的值（用props）：{{titleP}}</div>
    </div>
</template>

<script>
export default {
  name: 'ParentComponentA',
  props: {
    titleP: String,
    visible: {
      type: Boolean,
      default: false
    }},
  data () {
    return {
      title: '这是父组件A'
    }
  }}

</script>

<style scoped>

</style>
