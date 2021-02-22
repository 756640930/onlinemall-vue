<template>
  <div id="app">
    <tab-bar>
      <tab-bar-item></tab-bar-item>
      <tab-bar-item></tab-bar-item>
      <tab-bar-item></tab-bar-item>
      <tab-bar-item></tab-bar-item>
    </tab-bar>
  </div>
</template>

<script>

import TabBar from '@/components/common/TabBar.vue'
import TabBarItem from '@/components/common/tabBarItem.vue'

  
export default {
  name: 'App',
  components: {
    TabBar,
    TabBarItem
  }
}
</script>

<style>
    
</style>
