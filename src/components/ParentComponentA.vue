<template>
    <div style="border: 1px solid black">
        <h4>{{title}}</h4>
        <div>这个是父组件传进来的值（用props）：{{titleP}}</div>
        <button @click="changeParentColor()">点击按钮改变父组件的颜色</button>
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
  },
  methods: {
    changeParentColor () {
      this.$emit('fun', 'red')
    }
  }
}

</script>

<style scoped>

</style>
