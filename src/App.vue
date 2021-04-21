<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <DaBaby newName="This is my Test Component"/>
    <RecommendationBrowserComponent v-bind:recommendations="recs"></RecommendationBrowserComponent>
    
  </div>

  
</template>



<script>
import DaBaby from './components/DaBaby.vue'
import RecommendationBrowserComponent from './components/RecommendationBrowser.vue'


export default {
  name: 'App',
  components: {
    DaBaby,
    RecommendationBrowserComponent,
  
  },

  data(){
    return {
      recs: [
        {id: 1, brief: "Rec 1", content: "I am making this as long as possible due to the fact that I need to test out a long paragraph so I can see if it still looks good on the web page!"},
        {id: 2, brief: "Rec 2", content: "I am making this as long as possible due to the fact that I need to test out a long paragraph so I can see if it still looks good on the web page!"},
        {id: 3, brief: "Rec 3", content: "I am making this as long as possible due to the fact that I need to test out a long paragraph so I can see if it still looks good on the web page!"},
        {id: 4, brief: "Rec 4", content: "This is a test sentence"},
        {id: 5, brief: "Rec 5", content: "B"},
        {id: 6, brief: "Rec 6", content: "C"},
        {id: 7, brief: "Rec 7", content: "Yes"},
        {id: 8, brief: "Rec 8", content: "No"},
        {id: 9, brief: "Rec 9", content: "Maybe"},
        {id: 10, brief: "Rec 10", content: "Yes No Maybe"},
    
        

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
</style>
