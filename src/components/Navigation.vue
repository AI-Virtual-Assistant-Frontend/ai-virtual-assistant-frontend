<!-- This component creates the an interface for browsing the directory structure-->
<template>
  <div class="Navigation">
    <MongoDB ref="MongoInstance" v-on:directoryUpdate="getDirectories"/>
    <div class = "panel">
      <h3>Directory</h3> <button v-on:click="refresh">refresh</button>
      <div class = "subpanel">
        <div v-for="Directory in Directories" v-bind:key="Directory.id" align="left">
          <button class="buttonInvis" v-on:click="expand(Directory)"> > <b>{{ Directory.Name }}</b> </button>
          <div v-for="element in Directory.Contents" v-bind:key="element.id">
            <p> <button class="buttonInvis" v-on:click="expand(element)"><b>{{ element }}</b> </button> </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MongoDB from "./MongoDB.vue"

export default {
  components: {
    MongoDB
  },
  name: 'Navigation',
  data(){
    return{
      Directories: Array
    }
  },
  mounted() {
    this.refresh()
  },
  methods: {
    refresh(){
      this.$refs.MongoInstance.directoryUpdate()
    },
    expand(Directory){
      this.$refs.MongoInstance.subdirectoryUpdate(Directory)
    },
    getDirectories(Directories){
      console.log('Got from MongoDB', Directories)
      this.Directories = Directories
    },
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
.panel{
    width:220px;
    height:50vh;
    border-radius: 5px;
    background:rgba(155, 179, 247, 0.219);
}
.subpanel{
    height:84%;
    margin-top: 5px;
    margin-bottom: 5px;
    margin-left: 5px;
    margin-right: 5px;
    border-radius: 5px;
    background:rgba(155, 179, 247, 0.219);
}
p {
    white-space: pre;
    margin-top: 0;
    margin-bottom: 0;
    margin-left: 1em;
    margin-right: 0;
  }
</style>
