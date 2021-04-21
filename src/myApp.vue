<template>
  <div id="app">
    <AppPage />
  </div>
</template>

<script>
import AppPage from './components/AppPage'

export default {
  name: 'App',
  components: {
    AppPage
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
