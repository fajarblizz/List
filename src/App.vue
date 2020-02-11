<template>
  <div id="app">
    <TampilanList />
  </div>
</template>
<script>
import TampilanList from './components/TampilanList.vue'
export default {
  name: 'app',
  components: {
    TampilanList
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
  margin-left: 30px;
  margin-right: 30px;
}
</style>
