<template>
  <div id="app" class="container">

    <Input/>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Input from './components/Input.vue'
export default {
  name: 'App',
  components: {
    Input

  }
}
</script>

<style>
body {
  background: #fdfdfd !important;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  
}
</style>
