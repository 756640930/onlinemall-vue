<template>
  <div>
    <tab-bar>
      <tab-bar-item path="/home" activeColor="red">
        <img slot="item-icon" src="@/assets/img/img/home.svg" alt="" />
        <img slot="item-icon-active" src="@/assets/img/img/home_active.svg" alt="" />
        <div slot="item-text">首页</div>
      </tab-bar-item>
      <tab-bar-item path="/category" activeColor="red">
        <img slot="item-icon" src="@/assets/img/img/category.svg" alt="" />
        <img slot="item-icon-active" src="@/assets/img/img/category_active.svg" alt="" />
        <div slot="item-text">分类</div>
      </tab-bar-item>
      <tab-bar-item path="/cart" activeColor="red">
        <img slot="item-icon" src="@/assets/img/img/cart.svg" alt="" />
        <img slot="item-icon-active" src="@/assets/img/img/cart_active.svg" alt="" />
        <div slot="item-text">购物车</div>
      </tab-bar-item>
      <tab-bar-item path="/profile" activeColor="red">
        <img slot="item-icon" src="@/assets/img/img/profile.svg" alt="" />
        <img slot="item-icon-active" src="@/assets/img/img/profile_active.svg" alt="" />
        <div slot="item-text">我的</div>
      </tab-bar-item>
    </tab-bar>
  </div>
</template>

<script>

import TabBar from '@/components/common/tabbar/TabBar.vue'
import TabBarItem from '@/components/common/tabbar/tabBarItem.vue'

  
export default {
  name: 'MainTabBar',
  components: {
    TabBar,
    TabBarItem
  }
}
</script>

<style>

</style>
