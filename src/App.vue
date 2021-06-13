<template>
  <div id="app">
    <comments/>
  </div>
</template>

<script>
import comments from './components/Comments'
export default {
  name: 'App',
  components: {
    comments
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
