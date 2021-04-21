<template>
  <div class="recommendationBrowser">
    <h3>Recommendation Browser</h3>
    <div v-for="subrecommendation in recommendation.subrecommendations"
      v-bind:key="subrecommendation.id">
      <RecommendationBrowserBoxComponent
        :recommendation="subrecommendation"
        @selectRec="recSelected"
      />
    </div>
    <Popup v-show="isPopupVisible" @close="closePopup">
      <template v-slot:body>
        <TreeNode :currTree="selectedTree"/>
      </template>
    </Popup>
</div>
</template>

<script>
import RecommendationBrowserBoxComponent from './RecommendationBrowserBox.vue'
import TreeNode from './TreeNode'
import Popup from './Popup.vue'

export default {
  components: {
    TreeNode,
    RecommendationBrowserBoxComponent,
    Popup
  },
  name: 'RecommendationBrowserComponent',
  props: {
    recommendation: {
      type: Array,
      default: null
    }
  },
  methods: {
    recSelected(recommendation) {
      // emit selected event to sidebar
      this.$emit('selected');
      // make popup visible
      this.isPopupVisible = true;
      // find selected recommendation tree
      this.selectedTree = recommendation;
    },
    closePopup() {
      this.isPopupVisible = false;
    }
  },
  data() {
    return {
      isPopupVisible: false,
      selectedTree: null
    }
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
.recommendationBrowser {
  background: chartreuse;
  width: 100%;
}
</style>
