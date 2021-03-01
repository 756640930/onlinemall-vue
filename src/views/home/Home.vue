<template>
  <div>
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <feature-view></feature-view>
    <tab-control :title="['流行','新款','精选']" class="tab-control"></tab-control>
    <goods-list :goods="goods['pop'].list" ></goods-list>
  </div>
</template>

<script>

import NavBar from '@/components/common/navbar/NavBar.vue'
import {getHomeMultidata,getHomeGoodsList} from '@/network/home'
import HomeSwiper from '@/views/home/HomeSwiper'
import RecommendView from '@/views/home/RecommendView'
import FeatureView from '@/views/home/FeatureView.vue'
import GoodsList from '@/components/content/GoodsList.vue'
import TabControl from '@/components/content/TabControl.vue'



	export default {
		name: "Home",
    components: {
      NavBar,
      HomeSwiper,
      RecommendView,
      FeatureView,
      GoodsList,
      TabControl,
    },
    data() {
      return {
        banners: [],
        recommends: [],
        goods: {
          'pop': {page: 0, list: []},
          'new': {page: 0, list: []},
          'sell': {page: 0, list: []}
        }
      }
    },
    created() {
      this.getHomeMultidata();
      this.getHomeGoodsList('pop');
      this.getHomeGoodsList('new');
      this.getHomeGoodsList('sell');
    },
    methods: {
      getHomeMultidata(){
       getHomeMultidata().then(res =>{
        console.log(res.data)
        this.banners = res.data.banner.list
        this.recommends = res.data.recommend.list
        })
      },
      getHomeGoodsList(type) {
        const page = this.goods[type].page + 1
        getHomeGoodsList(type, page).then(res => {
          console.log(res)
          //push(...array)是将一个数组的元素全部push到另一个数组里
          this.goods[type].list.push(...res.data.list)
        })   
      }
    }
	}
</script>

<style scoped>
#home {
  padding-top: 44px;
}
.home-nav {
  /* 直接用在base.css定义的变量 */
  background-color: var(--color-tint);
  color: white;
  /* 让页头固定 */
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 9;
}
.tab-control {
  /* sticky作用是距离上边界44px的时候position自动变成fixed */
  position: sticky;
  top: 44px;
  background-color: white;
  z-index: 9;
}
</style>


