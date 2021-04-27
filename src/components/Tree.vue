<template>
  <div class="tree">
    <button @click="toggleExpand">
      <h2>{{ name }}</h2>
      <h4>{{ description }}</h4>
    </button>
    <div v-show="expanded" v-for="node in nodes" :key="node.name">
      <TreeNode :name="node.name" :description="node.description" :children="node.children" />
    </div>
  </div>
</template>

<script>
import TreeNode from './TreeNode.vue'

export default {
  name: 'Tree',
  components: {
    TreeNode
  },
  props: {
    name: String,
    description: String,
    nodes: Array
  },
  methods: {
    toggleExpand() {
      this.expanded = !this.expanded;
    }
  },
  data() {
    return {
      expanded: false
    }
  }
}
</script>

<style scoped>
.tree {
  margin: auto;
  width: 50%;
}
</style>