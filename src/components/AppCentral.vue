<template>
  <div class="outer">
    <div v-for="rec in recommendations" :key="rec.name" class="tree-button">
      <TreeNode :name="rec.name" :description="rec.description" :children="rec.children" class="tree"/>
    </div>
  </div>
</template>

<script>
import TreeNode from './TreeNode.vue'

export default {
  name: 'AppCentral',
  components: {
    TreeNode
  },
  data() {
    return {
      recommendations: [
        {
          name: 'Recommendation',
          description: 'Description',
          children: [
            {
              name: 'Reason1',
              description: 'Description',
              children: [
                {
                  name: 'Data1',
                  description: 'Description',
                  children: []
                },
                {
                  name: 'Data2',
                  description: 'Description',
                  children: []
                }
              ]
            }, 
            {
              name: 'Reason2',
              description: 'Description',
              children: [
                {
                  name: 'Data1',
                  description: 'Description',
                  children: []
                }
              ]
            }
          ]
        },
        {
          name: 'Recommendation',
          description: 'Description',
          children: [
            {
              name: 'Reason1',
              description: 'Description',
              children: [
                {
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
.outer {
 display: flex;
 flex-flow: row wrap;
 justify-content: space-between;
 margin: 20px;
}

.tree-button {
  /* display: flex; */
  /* flex-flow: row wrap; */
}

/* .tree {
  display: flex;
  flex-flow: column nowrap; */
/* } */
</style>
