<template>
  <div class="recommendationBrowser">
    <h3>Recommendation Browser</h3>
    <div v-for="(subrecommendation, index) in recommendation.subrecommendations"
      v-bind:key="subrecommendation.id">
      <b-row v-if="index%2==0" align-v="center">
        <b-col align-h="center">
          <RecommendationBrowserBoxComponent
            :recommendation="subrecommendation"
            @selectRec="recSelected"
          />
        </b-col>
        <b-col v-if="recommendation.subrecommendations[index+1]" align-h="center">
          <RecommendationBrowserBoxComponent
            :recommendation="recommendation.subrecommendations[index+1]"
            @selectRec="recSelected"
          />
        </b-col>
      </b-row>
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
      // make popup visible
      this.isPopupVisible = true;
      // emit selected event to open sidebar
      this.$emit('selected', this.isPopupVisible);
      // find selected recommendation tree
      this.selectedTree = recommendation;
    },
    closePopup() {
      // close Popup
      this.isPopupVisible = false;
      // emit event to close sidebar
      this.$emit('selected', this.isPopupVisible);
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
  border: 2px solid black;
  background: rgba(155, 179, 247, 0.219);
  width: 100%;
}
</style>
