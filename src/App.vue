<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    
    <sidebar style="float: right;"></sidebar>
    <navigation style="float: left;"></navigation>
    <recommendation-browser-component style="float: left;" v-bind:recommendations="recs"></recommendation-browser-component>
    <!-- <todoComponent msg="This message belongs to todoComponent.vue"/> -->
  </div>
</template>

<script>
// import todoComponent from './components/todoComponent.vue'
import RecommendationBrowserComponent from './components/RecommendationBrowser.vue'
import Navigation from './components/Navigation.vue'
import Sidebar from './components/Sidebar.vue'
//import RecommendationBrowserBoxComponent from './components/RecommendationBrowserBox.vue'

export default {
  name: 'App',
  components: {
    // todoComponent,
    //RecommendationBrowserBoxComponent
    RecommendationBrowserComponent,
    Navigation,
    Sidebar
  },
  data() {
    return {
      recs: [
        {id: 1, brief: "Rec 1", content: "This is the first recommendation. asdfasdf asdf asd asd fasd fasd fasdf asdf asf zdas fasf asd fasd f"},
        {id: 2, brief: "Rec 2", content: "This is the second recommendation."},
        {id: 3, brief: "Rec 3", content: "This is the third recommendation."},
        {id: 4, brief: "Rec 4", content: "This is the fourth recommendation."},
        {id: 5, brief: "Rec 5", content: "This is the fifth recommendation."},
        {id: 6, brief: "Rec 6", content: "This is the sixth recommendation."},
      ]
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
  display: flex;
}
.sidebar {
  display: flex;
}
.recommendation-browser-component {
  display: flex;
}
</style>
