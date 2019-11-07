<template>
    <div :style="{'background-color':backgroundColor}" id="app">
        {{ message }}
        <div>
            我准备在这放个父组件
            <!--fun在这绑定到组件上，当fun被触发的时候会调用changeBackgroundColor方法，子组件里的red作为实参传递到changeBackgroundColor方法的形参上-->
            <ParentComponentA :titleP="titleA" @fun="changeBackgroundColor"></ParentComponentA>
            <ParentComponentA :titleP="titleB"></ParentComponentA>

        </div>
    </div>

</template>

<script>
import ParentComponentA from './components/ParentComponentA'

export default {
  name: 'App',
  data () {
    return {
      message: '嗨！你好',
      titleA: '我是父组件的titleA',
      titleB: '我是父组件的titleB',
      backgroundColor: 'white'

    }
  },
  components: {ParentComponentA},
  methods: {
    // 这里的bc其实是子组件传过来的 red
    changeBackgroundColor (bc) {
      this.backgroundColor = bc
    }
  }
}
</script>

<style>
</style>
