<template>
  <div id="app">
    <div class="main">
      <div :class="[introScreen ? 'main-container--intro': '', 'main-container']">
        <Intro></Intro>
      </div>
    </div>
    <div class="sidebar-container">
      <Sidebar v-on:item-clicked="sidebarNavigation"></Sidebar>
    </div>
  </div>
</template>

<script>
import Intro from './components/Intro.vue';
import Sidebar from './components/Sidebar.vue';

export default {
  name: 'app',
  components: {
    Intro,
    Sidebar,
  },
  data() {
    return {
      introScreen: true,
      fincherScreen: false,
      wrightScreen: false,
      tarantinoScreen: false,
    }
  },
  methods: {
    sidebarNavigation(sidebarItem) {
      console.log(sidebarItem)
      switch(sidebarItem) {
        case 'Intro':
          this.introScreen = !this.introScreen
          this.fincherScreen = false
          this.wrightScreen = false
          this.tarantinoScreen = false
          break
        case 'Fincher':
          this.fincherScreen = !this.fincherScreen
          this.introScreen = false
          this.wrightScreen = false
          this.tarantinoScreen = false
          break
        case 'Wright':
          this.wrightScreen = !this.wrightScreen
          this.introScreen = false
          this.fincherScreen = false
          this.tarantinoScreen = false
          break
        case 'Tarantino':
          this.tarantinoScreen = !this.tarantinoScreen
          this.introScreen = false
          this.fincherScreen = false
          this.wrightScreen = false
          break
      }
    },
  },
};
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #FFFFFF;
  background-color: #2B2B31;
  height: 100vh;
  display: flex;
}
.main {
  width: 90%;
  margin: 3em 0 3em 3em;
  &-container {
    border: 2px solid #FFFFFF;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    &--intro {
      border: none
    }
  }
}
.sidebar-container {
  width: 10%;
  display: flex;
  justify-content: center;
}
</style>
