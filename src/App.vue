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
// import todoComponent from './components/todoComponent.vue'
// import RecommendationBrowserComponent from './components/RecommendationBrowser.vue'
import Navigation from './components/Navigation.vue'
import Sidebar from './components/Sidebar.vue'
//import RecommendationBrowserBoxComponent from './components/RecommendationBrowserBox.vue'

export default {
  name: 'App',
  components: {
    // todoComponent,
    //RecommendationBrowserBoxComponent
    // RecommendationBrowserComponent,
    Navigation,
    Sidebar
  },
  data() {
    return {
      // categoryRecommendation: 
      // {
      //   id: 1,
      //   brief: "Rec 1", 
      //   content: "This is the first recommendation. asdfasdf asdf asd asd fasd fasd fasdf asdf asf zdas fasf asd fasd f", 
      //   reasons: [
      //     {content: "This is reason 1.",
      //     evidence: [
      //       {content: "Evidence 1"},
      //       {content: "Evidence 2"},
      //     ]}
      //   ],
      //   subrecommendations: []
      // },

      // domainRecommendation:
      // {
      //   id: 2,
      //   brief: "Domain Recommendation.", 
      //   content: "You should invest in Employee Engagement", 
      //   reasons: [
      //     {content: "The Reason is that peer benchmarking shows...",
      //     evidence: [
      //       {content: "Evidence 1: 97% of peers..."},
      //       {content: "Evidence 2: More evidence for this reason."},
      //     ]}
      //   ],
      //   // subrecommendations: ["a", "b", "c"]
      //   subrecommendations: [this.testStr]
      // },
      // testStr: "What the ...?",
      //   testRec: {id:3, brief: "Test Rec", content: "This is a test recommendation.", subrecommendations: ["a", "b", "c"]},
        // {id:3, brief: "Rec 3", content: "This is the third recommendation."},
        // {id:4, brief: "Rec 4", content: "This is the fourth recommendation."},
        // {id:5, brief: "Rec 5", content: "This is the fifth recommendation."},
        // {id:6, brief: "Rec 6", content: "This is the sixth recommendation."},
      // ]
    }
  },
  methods: {
    testMethod(){

      // let categoryRecommendation = 
      // {
      //   brief: "Rec 1", 
      //   content: "This is the first recommendation. asdfasdf asdf asd asd fasd fasd fasdf asdf asf zdas fasf asd fasd f", 
      //   reasons: [
      //     {content: "This is reason 1.",
      //     evidence: [
      //       {content: "Evidence 1"},
      //       {content: "Evidence 2"},
      //     ]}
      //   ],
      // }

      // let domainRecommendation = 
      // {
      //   brief: "Domain Recommendation.", 
      //   content: "You should invest in Employee Engagement", 
      //   reasons: [
      //     {content: "The Reason is that peer benchmarking shows...",
      //     evidence: [
      //       {content: "Evidence 1: 97% of peers..."},
      //       {content: "Evidence 2: More evidence for this reason."},
      //     ]}
      //   ],
      //   subrecommendations: [categoryRecommendation]
      // }
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
