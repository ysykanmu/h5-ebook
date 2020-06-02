<template>
  <div class="home-free">
    <div class="home-free-header">{{title}}</div>
    <div class="home-free-content">
      <div class="home-free-item" v-for="(item,index) of freeData" :key="index">
        <van-image class="home-free-img" :lazy-load="true" :src="item.cover">
          <template v-slot:loading>
            <van-loading type="spinner" size="20" />
          </template>
        </van-image>
        <div class="home-free-text">
          <div class="book-title">{{item.title}}</div>
          <div class="book-title-author">
            <div class="book-author">{{item.author}}</div>
            <div class="book-author">{{item.categoryText}}</div>
          </div>
        </div>
      </div>
    </div>
    <div class="home-free-footer">
      <van-button round block class="home-free-btn">{{btnText}}</van-button>
    </div>
  </div>
</template>
 
<script>
export default {
  name: "HomeFree",
  props: {
    title: String,
    data: Array,
    btnText: {
      type: String,
      default: "换一批"
    }
  },
  computed: {
    freeData() {
      const _freeData = this.data.slice(0, 4);
      return _freeData;
    }
  }
};
</script>
 
<style lang="scss" scoped>
@import "../../assets/styles/global";
.home-free {
  padding: px2rem(16) px2rem(10) px2rem(20) px2rem(10);
  .home-free-header {
    font-size: px2rem(21);
    font-weight: bold;
    padding-left: px2rem(10);
  }
  .home-free-content {
    margin-top: px2rem(10.5);
    display: flex;
    flex-wrap: wrap;
    .home-free-item {
      flex: 0 0 50%;
      width: 50%;
      padding: 0 px2rem(10);
      box-sizing: border-box;
      margin-top: px2rem(12);
      display: flex;
      .home-free-img {
        width: 100%;
        min-height: px2rem(88);
      }
    }
    .home-free-text {
      flex: 0 0 60%;
      width: 60%;
      box-sizing: border-box;
      padding-left: px2rem(10);
      padding-right: px2rem(6);
      font-size: px2rem(14);

      word-break: break-word;
      display: flex;
      flex-direction: column;
      align-self: center;
      .book-title {
        line-height: px2rem(16.5);
        max-height: px2rem(32.3);
        overflow: hidden;
      }
      .book-title-author {
        margin-top: px2rem(8);
        line-height: px2rem(16.5);
        max-height: px2rem(36);
        color: #868686;
        overflow: hidden;
        .book-author {
          margin-top: px2rem(2);
          font-size: px2rem(12);
          max-height: px2rem(16);
          overflow: hidden;
        }
      }
    }
  }
  .home-free-footer {
    margin-top: px2rem(20);
    padding: 0 px2rem(10);
    .home-free-btn {
      color: #3696ef;
      font-size: px2rem(14);
    }
  }
}
</style>