<!-- This component creates the an interface for browsing the directory structure-->
<template>
  <div class="NavigationDirectory">
    <div v-if="Directory.open">
      <div :style="indent" align="left" v-for="element in Directory.subrecommendations" 
      v-bind:key="element.id">
        <p><button class="buttonInvis" v-on:click="expand(element)"><b>> {{ element.brief }}</b></button> </p>
        <navigation-directory v-bind:Directory="element" v-bind:depth="depth + 1"></navigation-directory>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  props: ['Directory', 'depth'],
  name: 'NavigationDirectory',
  data(){
    return{
      
    }
  },
  mounted() {
    this.refresh()
  },
  methods: {
    expand(Directory){
      this.$parent.expand(Directory)
    },
  },
  // Help from: https://vuejsdevelopers.com/2017/10/23/vue-js-tree-menu-recursive-components/
  computed: {
    indent() {
      return { transform: `translate(${this.depth * 10}px)`}
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
.buttonInvis {
  border: none;
  background-color: rgba(0, 0, 0, 0);
}
p {
    white-space: pre;
    margin-top: 0;
    margin-bottom: 0;
    margin-left: 1em;
    margin-right: 0;
  }
</style>
