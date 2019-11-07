<template>
    <div id="app">
        {{ message }}
        <div>
            我准备在这放个父组件
            <ParentComponentA :titleP="titleA"></ParentComponentA>
        </div>
    </div>

</template>

<script>
import ParentComponentA from './components/ParentComponentA'

export default {
  name: 'App',
  data () {
    return {message: '嗨！你好', titleA: '我是父组件的titleA'}
  },
  components: {ParentComponentA}
}
</script>

<style>
</style>
