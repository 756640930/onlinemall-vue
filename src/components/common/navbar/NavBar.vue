<template>
  <div class="nav-bar">
    <div class="left"><slot name="left"></slot></div>
    <div class="center"><slot name="center"></slot></div>
    <div class="right"><slot name="right"></slot></div>
  </div>
</template>

<script>
	export default {
		name: "NavBar",
    data() {
      return{
        
      }
    },
    methods: {

    }
	}
</script>

<style scoped>
.nav-bar {
  display: flex;
  line-height: 44px;
  height: 44px;
  box-shadow: 0px 1px 1px rgba(100,150,150,.1);
}
.left, .right {
  width: 60px;
}
.center {
  flex: 1;
  text-align: center;
}
</style>


