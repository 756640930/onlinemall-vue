<template>
  <div id="app">
    <router-view></router-view>
    <main-tab-bar></main-tab-bar>
  </div>
</template>

<script>

import MainTabBar from './components/common/tabbar/MainTabBar.vue'
  
export default {
  name: 'App',
  components: {
    MainTabBar
  }
}
</script>

<style>
  /* 在style里引用import要加@ */
  @import "./assets/css/base.css"
</style>
