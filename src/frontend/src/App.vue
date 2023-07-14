<template>
  <div id="app">
    <users-chart></users-chart>
  </div>
</template>

<script>
import UsersChart from './components/UsersChart.vue'

export default {
  name: 'App',
  components: {
    UsersChart
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
