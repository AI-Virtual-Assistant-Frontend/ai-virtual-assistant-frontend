<template>
  <div>
    <AppHeader class="header" />
    <Navigation class="navigation" @showSidebar="showSidebar" ref="navigation" v-bind:recommendations="domainRecommendation"></Navigation>
    <Sidebar class="sidebar" v-show="isSidebarVisible" @close="closeSidebar" />
  </div>
</template>

<script>
import AppHeader from './AppHeader'
import Sidebar from './Sidebar'
import Navigation from './Navigation'

export default {
  name: "AppPage",
  components: {
    AppHeader,
    Sidebar,
    Navigation
  },
  methods: {
    closeSidebar() {
      this.isSidebarVisible = false;
    },
    showSidebar(openOrClose) {
      this.isSidebarVisible = openOrClose;
    }
  },
  data() {
    return {
      isSidebarVisible: false
    }
  }

}
</script>

<style>
.navigation {
  float: left;
}
.sidebar {
  float: right;
}
</style>