<template>
  <div class="recommendationBrowser">
    <h3>Recommendation Browser</h3>
    <recommendation-browser-box-component 
      v-for="recommendation in recommendations"
      v-bind:key="recommendation.id"
      v-bind:recommendation="recommendation"></recommendation-browser-box-component>
  </div>
</template>

<script>
import RecommendationBrowserBoxComponent from './RecommendationBrowserBox.vue'

export default {
  components: {
    RecommendationBrowserBoxComponent
  },
  name: 'RecommendationBrowserComponent',
  props: ['recommendations'],
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
</style>
