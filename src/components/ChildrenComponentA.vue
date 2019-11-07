<template>
    <div style="border: 1px solid black">
        <h4>{{title}}</h4>
        <div>这个是{{myParent}}组件传进来的值（用props）：{{titleP}}</div>
        <button @click="changeParentColor()">点击按钮改变App组件的颜色</button>
    </div>
</template>

<script>
export default {
  name: 'ParentComponentA',
  props: {
    myParent: String,
    titleP: String,
    visible: {
      type: Boolean,
      default: false
    }},
  data () {
    return {
      title: '这是子组件A'
    }
  },
  methods: {
    // 当我点击按钮后进入的是组件内的方法
    changeParentColor () {
      // emit代表着向外部传参，在外部声明了一个事件叫fun，red是个实数
      this.$emit('fun', 'blue')
    }
  }
}

</script>

<style scoped>

</style>
