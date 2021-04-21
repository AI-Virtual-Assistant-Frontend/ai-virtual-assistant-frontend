<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    
    <sidebar ref="sidebar" style="float: right;"></sidebar>
    <!-- <navigation ref="navigation" style="float: left;" v-bind:recommendations="recommendations"></navigation> -->
    <navigation ref="navigation" style="float: left;" v-bind:recommendations="domainRecommendation"></navigation>
    <!-- <todoComponent msg="This message belongs to todoComponent.vue"/> -->
  </div>
</template>

<script>
import Navigation from './components/Navigation.vue'
import Sidebar from './components/Sidebar.vue'

export default {
  name: 'App',
  components: {
    Navigation,
    Sidebar
  },
  data() {
    return {

    }
  },
  methods: {
    testMethod(){

    }
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

/* .app {
  clear: both;
} */
.navigation {
  /* display: flex; */
  float: left;
}
.sidebar {
  float: right;
  /* display: flex; */
}
.recommendation-browser-component {
  display: flex;
}
</style>
