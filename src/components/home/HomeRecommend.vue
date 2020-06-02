<template>
  <div class="home-recommend">
    <div class="home-recommend-header">{{title}}</div>
    <div class="home-recommend-content">
      <div class="home-recommend-item" v-for="(item,index) of bookData" :key="index">
        <van-image class="home-recommend-img" :lazy-load="true" :src="item.cover">
          <template v-slot:loading>
            <van-loading type="spinner" size="20" />
          </template>
        </van-image>
        <div class="home-recommend-title">{{item.title}}</div>
      </div>
    </div>
    <div class="home-recommend-footer">
      <van-button round block class="home-recommend-btn">{{btnText}}</van-button>
    </div>
  </div>
</template>
 
<script>
export default {
  name: "HomeRecommend",
  props: {
    title: String,
    data: Array,
    btnText: {
      type: String,
      default: "换一批"
    }
  },
  computed: {
    bookData() {
      const _bookData = this.data.slice(0, 3);
      return _bookData;
    }
  },
  mounted() {
    console.log(this.data);
  }
};
</script>
 
<style lang="scss" scoped>
@import "../../assets/styles/global";
.home-recommend {
  margin-top: px2rem(20);
  padding: px2rem(13) px2rem(10) px2rem(20) px2rem(10);
  background: #f9f9f9;
  .home-recommend-header {
    font-size: px2rem(21);
    font-weight: bold;
    padding-left: px2rem(8);
  }
  .home-recommend-content {
    margin-top: px2rem(22.5);
    display: flex;
    .home-recommend-item {
      flex: 1;
      margin: 0 px2rem(8);
      min-height: px2rem(147);
      .home-recommend-img {
        width: 100%;
        min-height: px2rem(147);
      }
      .home-recommend-title {
        font-size: px2rem(14);
        line-height: px2rem(16.5);
        max-height: px2rem(32);
        overflow: hidden;
        word-break: break-word;
      }
    }
  }
  .home-recommend-footer {
    margin-top: px2rem(20);
    padding: 0 px2rem(10);
    .home-recommend-btn {
      color: #3696ef;
      font-size: px2rem(14);
    }
  }
}
</style>