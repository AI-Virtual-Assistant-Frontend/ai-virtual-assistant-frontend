<template>
  <div class="tree">
    <button @click="toggleExpand">
      <h1>{{ name }}</h1>
      <p>{{ description }}</p>
    </button>
    <div class="children" v-show="expanded" v-for="child in children" :key="child.name">
      <TreeNode :name="child.name" :description="child.description" :children="child.children" />
    </div>
  </div>
</template>
  
<script>
export default {
  name: 'TreeNode',
  props: {
    name: String,
    description: String,
    children: Object
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

.children {
  display: flex;
  flex-flow: row nowrap;
}
</style>