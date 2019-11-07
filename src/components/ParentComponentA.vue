<template>
    <div :style="{'background-color':backgroundColor}" style="border: 1px solid black">
        <h4>{{title}}</h4>
        <div>这个是App组件传进来的值（用props）：{{titleP}}</div>
        <button @click="changeParentColor()">点击按钮改变App组件的颜色</button>
        <div>在这放个ChildrenComponentA
            <ChildrenComponentA @fun="changeBackgroundColor"></ChildrenComponentA>
        </div>
    </div>
</template>

<script>
import ChildrenComponentA from './ChildrenComponentA'

export default {
  name: 'ParentComponentA',
  props: {
    titleP: String,
    visible: {
      type: Boolean,
      default: false
    }
  },
  data () {
    return {
      title: '这是父组件A',
      backgroundColor: 'yellow'
    }
  },
  components: {ChildrenComponentA},
  methods: {
    // 当我点击按钮后进入的是组件内的方法
    changeParentColor () {
      // emit代表着向外部传参，在外部声明了一个事件叫fun，red是个实数
      this.$emit('fun', 'red')
    },
    // 这里的bc其实是子组件传过来的 blue
    changeBackgroundColor (bc) {
      this.backgroundColor = bc
    }
  }
}

</script>

<style scoped>

</style>
