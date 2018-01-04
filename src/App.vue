<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
var mixin = {
  created: function () {
    console.log('混合对象的钩子被调用')
  }
}
var mixin2 = {
  created: function () {
    console.log('混合对象的钩子被调用2')
  }
}
export default {
  name: 'app',
  mixins: [mixin,mixin2],
  created: function () {
    console.log('组件钩子被调用')
  }
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
