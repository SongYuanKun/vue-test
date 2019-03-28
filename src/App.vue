<template>
  <div id="app">
   <resume></resume>
  </div>
</template>

<script>
import Resume from './components/resume/Resume'
export default {
  name: 'App',
  components: {Resume}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
