<template>
  <div id="app">
    <h1>Random Gif Cat</h1>
    <forms></forms>
  </div>
</template>

<script>
import Forms from './components/Forms.vue'

export default {
  name: 'App',
  components: {
    Forms
  }
}
</script>

<style>
*{
    margin:0;
    padding: 0;
}
body{
  background: #ADD9E6;
  text-align: center;
}
</style>
