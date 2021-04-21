<!-- This component creates the an interface for browsing the directory structure-->
<template>
<div/>
</template>

<script>
export default {
  components: {
  },
  name: 'MongoDB',
  methods: {
    directoryUpdate(){
        let dir1 = {
            Name: "Employee Engagement",
            Contents: null
        }
        let dir2 = {
            Name: "Revenue Management",
            Contents: null
        }
        this.$emit('directoryUpdate', [dir1, dir2])
    },
    subdirectoryUpdate(Directory){
        if (Directory.Contents != null){
            Directory.Contents = null
        }
        else{
            Directory.Contents = ["Recommendation 1", "Recommendation 2"]
        }
    }
  }
}
</script>
