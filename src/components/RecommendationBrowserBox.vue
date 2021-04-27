<template>
  <div class="recommendationBox">
    <div class=buttonDiv>
        <b-container>
          <b-card 
            v-bind:title="recommendation.brief"
            style="max-width:15rem"
            img-src="https://picsum.photos/600/300/?image=25"
            tag="article"
            class="cardStyle">
            <b-container class="tipped">
              <b-button v-on:click="selectRec">{{ recommendation.brief }}</b-button>
                <span class="tooltiptext">{{ recommendation.content }}</span>
            </b-container>
          </b-card>
        </b-container>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RecommendationBrowserBoxComponent',
  data() {
    return {
      selected: false,
    }
  },
  props: {
    recommendation: {
      type: Object
    }
  },
  methods: {
    selectRec() {
      this.$emit('selectRec', this.recommendation);
    }
  }
}
</script>

<style scoped>
.buttonDiv {
  display: inline-block;
  vertical-align: bottom;
  margin: 5px 0px;
}
button {
  background-color: #F4Be4C;
  border: 2px solid #002C3A;
  color: #002C3A;
  text-align: center;
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
</style>
