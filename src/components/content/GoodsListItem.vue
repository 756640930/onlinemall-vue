<template>
  <div class="goods-item">
    <img :src="goodsItem.show.img" alt="" />
    <div class="goods-info">
      <p>{{goodsItem.title}}</p>
      <span class="price">{{goodsItem.price}}</span>
      <span class="collect">{{goodsItem.cfav}}</span>
    </div>
  </div>
</template>

<script>
	export default {
		name: "GoodsListItem",
    props: {
      goodsItem: {
        type: Object,
        default() {
          return {}
        }
      }
    }
	}
</script>

<style scoped>
.goods-item {
  padding-bottom: 35px;
  position: relative;
  width: 48%;
}
.goods-item img {
  width: 100%;
  /* 圆角边框 */
  border-radius: 5px;
}
.goods-info {
  /* 子绝父相:父元素是绝对定位，子元素相对定位，这样才能用bottom，right，left来定位子元素位于父元素中的位置 */
  position: absolute;
  bottom: 5px;
  left: 0;
  right: 0;
  font-size: 12px;
  overflow: hidden;
  text-align: center;
}
  .goods-info p {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin-bottom: 3px;
  }

  .goods-info .price {
    color: var(--color-high-text);
    margin-right: 20px;
  }

  .goods-info .collect {
    position: relative;
  }

  .goods-info .collect::before {
    content: '';
    position: absolute;
    left: -15px;
    top: 0;
    width: 14px;
    height: 14px;
    background: url("~/assets/img/img/collect.svg") 0 0/14px 14px;
  }
</style>


