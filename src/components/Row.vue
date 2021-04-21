<template>
<div>
 
    <b-row align-v="center">
        <b-col align-h="center">  <recommendation-browser-box-component v-bind:recommendation="single[0]"></recommendation-browser-box-component> </b-col>
        <b-col align-h="center">  <recommendation-browser-box-component v-bind:recommendation="single[1]">></recommendation-browser-box-component>  </b-col> 
    </b-row>
</div>
</template>

<script>


import RecommendationBrowserBoxComponent from './RecommendationBrowserBox.vue'


export default {
     created(){
     var allTheArrays = []

      //for loop that creates sub-arrays
      var i
      for (i = 0; i < this.recs.length; i += 2){
        allTheArrays.push(this.recs.slice(i, i+2))
      }

      this.these = allTheArrays

  },
    
    components:{
       RecommendationBrowserBoxComponent,
    },
    name: 'RowComp',
    
    props: ["single"],

    methods: { 

        

    }

    //props:{ }
}


</script>
