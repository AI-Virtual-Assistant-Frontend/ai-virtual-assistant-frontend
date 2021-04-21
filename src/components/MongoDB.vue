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
        let lowestLevelRecommendation = 
        {
            open: false,
            brief: "Lowest Level Recommendation", 
            content: "This is a lowest level recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is a reason for this lowest level recommendation.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence 1 for lowest level reason"},
                    {brief: 'Evidence 2', content: "Evidence 2 for lowest level reason"},
                    {brief: 'Evidence 3', content: "Evidence 3 for lowest level reason"},
                ]}
            ],
            subrecommendations: []
        }
        let lowerLevelRecommendation = 
        {
            open: false,
            brief: "Lower Level Recommendation", 
            content: "This is a lower level recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is a reason for this lower level recommendation.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence 1 for lower level reason"},
                    {brief: 'Evidence 2', content: "Evidence 2 for lower level reason"},
                    {brief: 'Evidence 3', content: "Evidence 3 for lower level reason"},
                ]}
            ],
            subrecommendations: [lowestLevelRecommendation]
        }
        let lowLevelRecommendation = 
        {
            open: false,
            brief: "Low Level Recommendation", 
            content: "This is a low level recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is a reason for this low level recommendation.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence 1 for low level reason"},
                    {brief: 'Evidence 2', content: "Evidence 2 for low level reason"},
                ]}
            ],
            subrecommendations: [lowerLevelRecommendation]
        }
        let lowLevelRecommendation2 = 
        {
            open: false,
            brief: "Low Level Recommendation 2", 
            content: "This is a second low level recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is a reason for this low level recommendation.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence 1 for low level reason"},
                    {brief: 'Evidence 2', content: "Evidence 2 for low level reason"},
                ]}
            ],
            subrecommendations: []
        }
        let categoryRecommendation = 
        {
            open: false,
            brief: "Category Recommendation", 
            content: "This is a category recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is reason 1.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence 1"},
                    {brief: 'Evidence 2', content: "Evidence 2"},
                ]}
            ],
            subrecommendations: [lowLevelRecommendation]
        }
        let categoryRecommendation2 = 
        {
            open: false,
            brief: "Category Recommendation 2", 
            content: "This is a second category recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is yet another reason.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence"},
                    {brief: 'Evidence 2', content: "More evidence"},
                ]}
            ],
            subrecommendations: [lowLevelRecommendation2]
        }
        let categoryRecommendation3 = 
        {
            open: false,
            brief: "Category Recommendation 3", 
            content: "This is a third category recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is yet another reason.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence"},
                    {brief: 'Evidence 2', content: "More evidence"},
                ]}
            ],
            subrecommendations: []
        }
        let categoryRecommendation4 = 
        {
            open: false,
            brief: "Category Recommendation 4", 
            content: "This is a fourth category recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is yet another reason.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence"},
                    {brief: 'Evidence 2', content: "More evidence"},
                ]}
            ],
            subrecommendations: []
        }
        let categoryRecommendation5 = 
        {
            open: false,
            brief: "Category Recommendation 5", 
            content: "This is a fifth category recommendation", 
            children: [
                { brief: 'Reason 1',
                content: "This is yet another reason.",
                children: [
                    {brief: 'Evidence 1', content: "Evidence"},
                    {brief: 'Evidence 2', content: "More evidence"},
                ]}
            ],
            subrecommendations: []
        }
        let domainRecommendation = 
        {
            open: false,
            brief: "Domain Recommendation", 
            content: "You should invest in Employee Engagement", 
            children: [
                { brief: 'Reason 1',
                content: "The Reason is that peer benchmarking shows...",
                children: [
                    {brief: 'Evidence 1', content: "Evidence 1: 97% of peers..."},
                    {brief: 'Evidence 2', content: "Evidence 2: More evidence for this reason."},
                ]}
            ],
            // subrecommendations: ["a", "b", "c"]
            subrecommendations: [categoryRecommendation, categoryRecommendation2]
        }
        let domainRecommendation2 = 
        {
            open: false,
            brief: "Domain Recommendation 2", 
            content: "You should invest in some other domain...", 
            children: [
                { brief: 'Reason 1',
                content: "The Reason is that something something...",
                children: [
                    {brief: 'Evidence 1', content: "Evidence 1: some evidence 1..."},
                    {brief: 'Evidence 2', content: "Evidence 2: some evidence 2..."},
                    {brief: 'Evidence 3', content: "Evidence 3: some evidence 3..."},
                ]}
            ],
            // subrecommendations: ["a", "b", "c"]
            subrecommendations: [categoryRecommendation3, categoryRecommendation4, categoryRecommendation5]
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