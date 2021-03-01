<template>
  <div class="goods-list">
    <goods-list-item v-for="(item,index) in goods" :key="index" :goodsItem="item"></goods-list-item>
  </div>
</template>

<script>
import GoodsListItem from '@/components/content/GoodsListItem.vue'
	export default {
  components: { GoodsListItem },
		name: "GoodsList",
    props: {
      goods: {
        type: Array,
        default() {
          return []
        }
      }
    },
	}
</script>

<style scoped>
  .goods-list {
    display: flex;
    /* flex-wrap的作用页面根据元素的大小自动进行flex布局，而不是全部塞到一行里 */
    flex-wrap: wrap;
    /* flex布局内元素间隔均匀 */
    justify-content: space-around;
    padding: 2px;
  }
</style>


