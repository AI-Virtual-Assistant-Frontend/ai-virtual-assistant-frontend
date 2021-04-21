<template>
  <b-container>
    <b-card 
      v-bind:title="recommendation.brief"
      style="max-width:15rem"
      img-src="https://picsum.photos/600/300/?image=25"
      tag="article"
      class="cardStyle">
      <b-container class="tipped">
        <b-button v-on:click="toggleSelect">{{ recommendation.brief }}</b-button>
          <span class="tooltiptext">{{ recommendation.content }}</span>
      </b-container>
    </b-card>
  </b-container>
  

</template>

<script>
//import $ from 'jquery'
export default {
  name: 'RecommendationBrowserBoxComponent',
  data() {
    return {
      selected: false,
    }
  },
  props: ['recommendation'],
  methods: {
    reverseMessage: function() {
      this.recommendation.brief = this.recommendation.brief.split('').reverse().join('')
    },
    toggleSelect: function() {
      this.selected = !this.selected
    },

  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


.recommendationBox {
  text-align: left;
  background-color: #006CBA;
  border: 2px solid #002C3A;
  margin: 0px 30%;
}
.buttonDiv {
  /* float: left; */
  display: inline-block;
  vertical-align: bottom;
}
button {
  background-color: #F4Be4C;
  border: 2px solid #002C3A;
  color: #002C3A;
  text-align: center;
  padding: 10px 10px;
  margin: 10px 10px;
  font-size: 16px;

  transition-delay: 0.0s;
  transition-duration: 0.4s;
}

.cardStyle {
  max-width: 20rem;

}

button:hover {
  background-color: #D49e2C;
}
.recommendationDetails {
  background-color: #006CBA;
  color:#F4Be4C;
  margin: 0px 5px;
  vertical-align: middle;
  display: inline-block;
}

.tipped {
		position: relative;
}

.tipped .tooltiptext {
		visibility: hidden;
		width: 500px;
    
		background-color: black;
    color: orange;
		text-align: center;
    border-width: 10px;
    border-color: purple;
		padding: 5px;
		border-radius: 3px;
		position: absolute;
		top: 10%;
		left: 75%;
		z-index: 1;
}
.tipped:hover .tooltiptext {
		visibility: visible;
	}

/* .recommendationDetails:hover {
  bottom: 0;
  height: 100%;
} */
</style>
