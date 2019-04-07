<template>
  <div id="app">
    <div class="main">
      <div :class="[introScreen ? 'main-container--intro': '', 'main-container']">
        <template v-if="introScreen">
          <Intro></Intro>
        </template>
        <template v-else-if="fincherScreen">
          <FincherScreen></FincherScreen>
        </template>
        <template v-else-if="wrightScreen">
          <WrightScreen></WrightScreen>
        </template>
        <template v-else-if="tarantinoScreen">
          <TarantinoScreen></TarantinoScreen>
        </template>
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
import FincherScreen from './components/FincherScreen.vue';
import WrightScreen from './components/WrightScreen.vue';
import TarantinoScreen from './components/TarantinoScreen.vue';

export default {
  name: 'app',
  components: {
    Intro,
    Sidebar,
    FincherScreen,
    WrightScreen,
    TarantinoScreen
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
  font-family: 'Inconsolata', monospace;
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
