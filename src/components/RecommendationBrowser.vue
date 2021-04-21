<template>
  <div class="recommendationBrowser">
    <h3>Recommendation Browser</h3>
    <div 
      v-for="recommendation in recommendations"
      v-bind:key="recommendation.id"
    >
      <RecommendationBrowserBoxComponent
        :recommendation="recommendation"
        :recTree="recs[0]"
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
    recommendations: {
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
      this.recs.filter(obj => {
        if (obj.id == recommendation.id) {
          this.selectedTree = obj;
        }
      });
    },
    closePopup() {
      this.isPopupVisible = false;
    }
  },
  data() {
    return {
      isPopupVisible: false,
      selectedTree: null,
      recs: [
        {
          id: 1,
          name: 'Recommendation',
          description: 'Description',
          children: [
            {
              id: 1,
              name: 'Reason1',
              description: 'Description',
              children: [
                {
                  id: 1,
                  name: 'Data1',
                  description: 'Description',
                  children: []
                },
                {
                  id: 2,
                  name: 'Data2',
                  description: 'Description',
                  children: []
                }
              ]
            }, 
            {
              id: 2,
              name: 'Reason2',
              description: 'Description',
              children: [
                {
                  id: 1,
                  name: 'Data1',
                  description: 'Description',
                  children: []
                }
              ]
            }
          ]
        },
        {
          id: 2,
          name: 'Recommendation',
          description: 'Description',
          children: [
            {
              id: 1,
              name: 'Reason1',
              description: 'Description',
              children: [
                {
                  id: 1,
                  name: 'Data1',
                  description: 'Description',
                  children: []
                }
              ]
            }
          ]
        }
      ]
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
  /* background: chartreuse; */
  /* margin: 0px 40%; */
  width: 100%;
}
</style>
