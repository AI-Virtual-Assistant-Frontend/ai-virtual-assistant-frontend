<template>
  <div>
      <AppHeader class="header" />
      <div class="middle">
        <Navigation class="directory" />
        <!-- <AppCentral /> -->
        <RecommendationBrowserComponent :recommendations="recommendations" @selected="openSidebar"/>
        <Sidebar v-show="isSidebarVisible" @close="closeSidebar" class="sidebar" />
      </div>
      <AppFooter class="footer" />
  </div>
</template>

<script>
// import AppCentral from './AppCentral'
import AppHeader from './AppHeader'
import AppFooter from './AppFooter'
import Sidebar from './Sidebar'
// import AppDirectory from './components/AppDirectory',
import Navigation from './Navigation'
import RecommendationBrowserComponent from './RecommendationBrowser'

export default {
  name: "AppPage",
  components: {
    // AppCentral,
    AppHeader,
    AppFooter,
    Sidebar,
    Navigation,
    RecommendationBrowserComponent
  },
  methods: {
    openSidebar() {
      this.isSidebarVisible = true;
    },
    closeSidebar() {
      this.isSidebarVisible = false;
    }
  },
  data() {
    return {
      isSidebarVisible: false,
      recommendations: [
        {id: 1, brief: "Rec 1", content: "This is the first recommendation. asdfasdf asdf asd asd fasd fasd fasdf asdf asf zdas fasf asd fasd f"},
        {id: 2, brief: "Rec 2", content: "This is the second recommendation."},
        {id: 3, brief: "Rec 3", content: "This is the third recommendation."},
        {id: 4, brief: "Rec 4", content: "This is the fourth recommendation."},
        {id: 5, brief: "Rec 5", content: "This is the fifth recommendation."},
        {id: 6, brief: "Rec 6", content: "This is the sixth recommendation."},
      ],
    }
  }

}
</script>

<style scoped>
.header, .footer {
  padding: 20px 0px 20px 0px;
}

.middle {
  display: grid;
  grid-template-columns: 220px auto 220px;
  height: 750px;
}

.directory {
  grid-column: 1;
}

.header {
  border-bottom: 5px solid black;
  grid-column: 2;
}

.sidebar {
  grid-column: 3;
}

.footer {
}
</style>