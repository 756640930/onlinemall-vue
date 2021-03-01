<template>
  <div class="recommend-view">
    <div v-for="(item,index) in recommends" :key="index" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image" alt="" />
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>




	export default {
		name: "RecommendView",
    props: {
      recommends: {
        type: Array,
        default: []
      }
    },
    components: {
    },
    data() {
      return {
      }
    }
	}
</script>

<style scoped>
.recommend-view {
  display: flex;
  /* text-align作用是让内部的div居中 */
  text-align: center;
  font-size: 13px;
  padding: 15px 0 20px;
  /* 下边框 */
  border-bottom: 10px solid rgb(231, 228, 228);
}
.recommend-item {
  /* flex布局内部的div用flex：1则均等分 */
  flex: 1;
}
.recommend-item img {
  width: 70px;
  height: 70px;
  margin-bottom: 5px;
}
</style>


