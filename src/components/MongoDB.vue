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
        // let dir1 = {
        //     Name: "dir 1",
        //     Contents: null
        // }
        // let dir2 = {
        //     Name: "dir 2",
        //     Contents: null
        // }
        let lowLevelRecommendation = 
        {
            id: 3,
            open: false,
            brief: "Low Level Recommendation", 
            content: "This is a low level recommendation", 
            reasons: [
            {content: "This is a reason for this low level recommendation.",
            evidence: [
                {content: "Evidence 1 for low level reason"},
                {content: "Evidence 2 for low level reason"},
            ]}
            ],
            subrecommendations: []
        }
        let categoryRecommendation = 
        {
            id: 1,
            open: false,
            brief: "Category Recommendation", 
            content: "This is a category recommendation", 
            reasons: [
            {content: "This is reason 1.",
            evidence: [
                {content: "Evidence 1"},
                {content: "Evidence 2"},
            ]}
            ],
            subrecommendations: [lowLevelRecommendation]
        }
        let categoryRecommendation2 = 
        {
            id: 5,
            open: false,
            brief: "Category Recommendation 2", 
            content: "This is a second category recommendation", 
            reasons: [
            {content: "This is yet another reason.",
            evidence: [
                {content: "Evidence"},
                {content: "More evidence"},
            ]}
            ],
            subrecommendations: [lowLevelRecommendation]
        }
        let domainRecommendation = 
        {
            id: 2,
            open: false,
            brief: "Domain Recommendation", 
            content: "You should invest in Employee Engagement", 
            reasons: [
            {content: "The Reason is that peer benchmarking shows...",
            evidence: [
                {content: "Evidence 1: 97% of peers..."},
                {content: "Evidence 2: More evidence for this reason."},
            ]}
            ],
            // subrecommendations: ["a", "b", "c"]
            subrecommendations: [categoryRecommendation, categoryRecommendation2]
        }
        let domainRecommendation2 = 
        {
            id: 4,
            open: false,
            brief: "Domain Recommendation 2", 
            content: "You should invest in some other domain...", 
            reasons: [
            {content: "The Reason is that something something...",
            evidence: [
                {content: "Evidence 1: some evidence 1..."},
                {content: "Evidence 2: some evidence 2..."},
                {content: "Evidence 3: some evidence 3..."},
            ]}
            ],
            // subrecommendations: ["a", "b", "c"]
            subrecommendations: []
        }
        let recList = {
            open: true,
            subrecommendations: [domainRecommendation, domainRecommendation2]
        }
        // this.$emit('directoryUpdate', [dir1, dir2])
        this.$emit('directoryUpdate', recList)
    },
    subdirectoryUpdate(Directory){
        if (Directory.open) {
            Directory.open = false;
        } else {
            Directory.open = true;
        }
        // if (Directory.Contents != null){
        //     Directory.Contents = null
        // }
        // else{
        //     Directory.Contents = ["Recommendation 1", "Recommendation 2"]
        // }
    }
  }
}
</script>
