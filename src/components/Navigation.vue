<!-- This component creates the an interface for browsing the directory structure-->
<template>
  <div class="Navigation">
    <MongoDB ref="MongoInstance" v-on:directoryUpdate="getDirectories"/>
    <div class = "panel">
      <h3>Directory</h3> <button v-on:click="refresh">refresh</button>
      <div class = "subpanel">
        <navigation-directory v-bind:Directory="Directories" v-bind:depth="0"></navigation-directory>
      </div>
    </div>
    
    <div class = "central">
      <recommendation-browser-component @selected="showSidebar" ref="recommendationBrowser" style="float: left;" v-bind:recommendation="SelectedRecommendation"></recommendation-browser-component>
    </div>
  </div>
</template>

<script>
import NavigationDirectory from "./NavigationDirectory.vue"
import MongoDB from "./MongoDB.vue"
import RecommendationBrowserComponent from './RecommendationBrowser.vue'

export default {
  components: {
    NavigationDirectory,
    MongoDB,
    RecommendationBrowserComponent
  },
  name: 'Navigation',
  data(){
    return{
      Directories: Array,
      SelectedRecommendation: Object
    }
  },
  mounted() {
    this.refresh()
  },
  methods: {
    showSidebar(openOrClose) {
      this.$emit('showSidebar', openOrClose);
    },
    refresh(){
      this.$refs.MongoInstance.directoryUpdate()
    },
    expand(Directory){
      this.$refs.MongoInstance.subdirectoryUpdate(Directory)
      this.SelectedRecommendation = Directory;
    },
    getDirectories(Directories){
      console.log('Got from MongoDB', Directories)
      this.Directories = Directories
    },
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
.buttonInvis {
  border: none;
  background-color: rgba(0, 0, 0, 0);
}
.panel{
    float: left;
    width:25vw;
    height:50vh;
    border-radius: 5px;
    background:rgba(155, 179, 247, 0.219);
}
.subpanel{
    height:84%;
    margin-top: 5px;
    margin-bottom: 5px;
    margin-left: 5px;
    margin-right: 5px;
    border-radius: 5px;
    background:rgba(155, 179, 247, 0.219);
}
.central{
  float: right;
  width: 50vw;
  position: relative;
  /* right: -100px; */
}
p {
    white-space: pre;
    margin-top: 0;
    margin-bottom: 0;
    margin-left: 1em;
    margin-right: 0;
  }
</style>