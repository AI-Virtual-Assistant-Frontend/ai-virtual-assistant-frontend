<template>
  <div class="recommendationBrowser">
    <h3>Recommendation Browser</h3>
    <!-- <p>{{recommendation.subrecommendations}}</p> -->
    <div v-for="subrecommendation in recommendation.subrecommendations"
      v-bind:key="subrecommendation.id">
      <recommendation-browser-box v-bind:recommendation="subrecommendation"></recommendation-browser-box>
    </div>
    <recommendation-browser-box-component 
      v-for="subrecommendation in recommendation.subrecommendations"
      v-bind:key="subrecommendation.id"
      v-bind:recommendation="subrecommendation"></recommendation-browser-box-component>
  </div>
</template>

<script>
import RecommendationBrowserBox from './RecommendationBrowserBox.vue'
// import RecommendationBrowserBoxComponent from './RecommendationBrowserBox.vue'

export default {
  components: {
    RecommendationBrowserBox
  },
  name: 'RecommendationBrowserComponent',
  props: ['recommendation'],
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
a {
  color: #42b983;
}
.recommendationBrowser {
  background: chartreuse;
  /* margin: 0px 40%; */
  width: 100%;
}
</style>
