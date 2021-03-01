<template>
  <div class="tab-control">
    <div v-for="(item,index) in title" :key="index" class="tab-control-item" :class="{active: index===currentIndex}" @click="tabClick(index)">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>

	export default {
  components: {  },
		name: "TabControl",
    props: {
      title: {
        type: Array,
        default() {
          return []
        }
      }
    },
    data() {
      return {
        currentIndex: 0

      }
    },
    methods: {
      tabClick(index) {
        this.currentIndex = index;
      }
    }
	}
</script>

<style scoped>
  .tab-control {
    display: flex;
    text-align: center;
    height: 40px;
    /* 行高 */
    line-height: 40px;
  }
  .tab-control-item {
    /* 平分 */
    flex: 1;
  }
  .tab-control-item span {
    padding: 3px;
  }
  .active {
    color: var(--color-high-text)
  }
  .active span {
    border-bottom: 3px solid var(--color-tint);
  }
</style>


