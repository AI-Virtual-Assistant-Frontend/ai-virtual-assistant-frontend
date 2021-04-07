<template>
  <div class="recommendationBox">
    <div class=buttonDiv>
      <button v-on:click="toggleSelect">{{ recommendation.brief }}</button>
    </div>
    <div v-if="selected" class="recommendationDetails">
      <h3>{{recommendation.brief}}</h3>
      <p>{{recommendation.content}}</p>
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
  props: ['recommendation'],
  methods: {
    reverseMessage: function() {
      this.recommendation.brief = this.recommendation.brief.split('').reverse().join('')
    },
    toggleSelect: function() {
      this.selected = !this.selected
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


.recommendationBox {
  text-align: left;
  background-color: #006CBA;
  border: 2px solid #002C3A;
  margin: 0px 5%;
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
  padding: 64px 32px;
  margin: 10px 10px;
  font-size: 16px;

  transition-delay: 0.0s;
  transition-duration: 0.4s;
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
/* .recommendationDetails:hover {
  bottom: 0;
  height: 100%;
} */
</style>
