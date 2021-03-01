<template>
  <div class="tab-bar-item" @click="itemClick()">
    <!-- 用两个插槽来显示点击和不点击时候的两种图片 -->
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <!-- 动态绑定样式 -->
    <!-- <div :class="{active:isActive}"><slot name="item-text"></slot></div> -->
    <!-- 如果想将css样式的具体内容由js变量决定，那么就只能用:style动态绑定样式 -->
    <div :style="activeStyle"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
	export default {
		name: "tabBarItem",
    props: {
      path: String,
      activeColor: {
        type: String,
        default: "red"
      }
    },
    data() {
      return{
        
      }
    },
    computed: {
      isActive() {
        return this.$route.path == this.path
      },
      activeStyle() {
        return this.isActive ? {color: this.activeColor} : {}
      }
    },
    methods: {
      itemClick() {
        this.$router.replace(this.path)
        // 注意这里面的this.$router和this.$route不一样,This.$route指的是路由配置文件index中的路由数组routes的元素
        // console.log(this.$route.path)
        // console.log(this.$router)
      }
    }
	}
</script>

<style scoped>
  .tab-bar-item {
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 14px;
  }

  .tab-bar-item img {
    width: 24px;
    height: 24px;
    margin-top: 3px;
    /* 图片下默认有三像素间隔（去掉） */
    vertical-align: middle;
    margin-bottom: 2px;
  }
  /* .active {
    color: red
  } */
</style>


