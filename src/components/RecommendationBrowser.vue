<template>
  <div class="recommendationBrowser">
    <h3>Recommendation Browser</h3>
    <b-row align-h="center">
      <row-comp
      v-for="(row,index) in rows"
      v-bind:key="index"
      v-bind:single="row"></row-comp>
    </b-row>
     
  </div>
</template>

<script>
//import RecommendationBrowserBoxComponent from './RecommendationBrowserBox.vue'
import RowComp from './Row.vue'

export default {

  created(){
     var allTheArrays = []

      //for loop that creates sub-arrays
      var i
      for (i = 0; i < this.recommendations.length; i += 2){
        allTheArrays.push(this.recommendations.slice(i, i+2))
      }

      this.rows = allTheArrays

  },
  components: {
    //RecommendationBrowserBoxComponent,
    RowComp
    
  },
  name: 'RecommendationBrowserComponent',
  props: ['recommendations', 'rows'],

  methods:{
    
  }
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
