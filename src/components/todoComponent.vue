<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      TODO:
    </p>
    <div class="incomplete">
      <h1>Incomplete:</h1>
      <p>
      <ul>
        <li>- RecommendationBrowser: Receive recommendations (Objects, Strings?) as input to Component</li>
        <li>- RecommendationBrowser: Display a box in center of screen for each recommendation passed in</li>
        <li>- RecommendationBrowser: Display the shortened recommendation (passed in from Rec object? or generated locally?) in each box</li>
        <li>- RecommendationBrowser: Allow users to click each recommendation box</li>
        <li>- RecommendationBrowser: Invoke Recommendation Tree display when recommendation box clicked</li>
      </ul>
      </p>
    </div>
    <div class="completed">
      <h1>Complete:</h1>
      <p>
        - 
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'todoComponent',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  display: inline-block;
  list-style-type: none;
  padding: 0;
}
li {
  text-align: left;
  padding: 2px;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.completed {
  color: green
}
.incomplete {
  color: red
}
</style>
