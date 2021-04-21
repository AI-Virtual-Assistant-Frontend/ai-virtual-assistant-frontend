<template>
  <div class="tree">
    <button @click="toggleExpand">
      <h1>{{ currTree.brief }}</h1>
      <p>{{ currTree.content }}</p>
    </button>
    <div class="same-level">
      <div class="children" v-show="expanded" v-for="child in currTree.children" :key="child.name">
        <TreeNode :currTree="child" />
      </div>
    </div>
  </div>
</template>
  
<script>
export default {
  name: 'TreeNode',
  props: {
    // name: String,
    // description: String,
    // children: Object
    currTree: Object
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
  display: flex;
  flex-flow: column nowrap;
}

.same-level {
  display: flex;
}
</style>