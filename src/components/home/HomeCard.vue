<template>
  <div class="home-card">
    <div class="home-card-inner">
      <div class="home-info">
        <van-image
          class="home-info-avatar"
          :round="true"
          :lazy-load="true"
          :src="`https://www.youbaobao.xyz/mpvue-res/logo.jpg`"
        >
          <template v-slot:loading>
            <van-loading type="spinner" size="20" />
          </template>
        </van-image>
        <span class="home-info-name">止于终老</span>
        <span class="home-info-hint">书架共0本好书 • 特别精选</span>
      </div>
      <div class="home-card-book">
        <div class="home-card-img-wrapper">
          <div class="home-card-img-item" v-for="(item,index) of data" :key="index">
            <van-image class="home-card-img" :lazy-load="true" :src="item.cover">
              <template v-slot:loading>
                <van-loading type="spinner" size="20" />
              </template>
            </van-image>
          </div>
        </div>
        <div class="home-card-shelf-wrapper">
          <div class="home-card-shelf">书架</div>
          <van-icon class="arrow" name="arrow"></van-icon>
        </div>
      </div>
    </div>
  </div>
</template>
 
<script>
export default {
  name: "HomeCard",
  props: {
    data: Array
  },
  methods: {}
};
</script>
 
<style lang="scss" scoped>
@import "../../assets/styles/global";
.home-card {
  background: #54575f;
  margin: px2rem(35) px2rem(20) 0 px2rem(20);
  border-radius: px2rem(10);
  .home-card-inner {
    padding: px2rem(20) px2rem(8) px2rem(20) px2rem(10);
    box-sizing: border-box;
    .home-info {
      display: flex;
      align-items: center;
      padding-left: px2rem(10);
      .home-info-avatar {
        width: px2rem(20);
      }
      .home-info-name {
        display: block;
        padding: 0 px2rem(8.5);
        font-size: px2rem(12);
        color: #ffffff;
        white-space: nowrap;
      }
      .home-info-hint {
        font-size: px2rem(12);
        color: #ffffff;
        opacity: 0.7;
        white-space: nowrap;
      }
    }
    .home-card-book {
      display: flex;
      margin-top: px2rem(18.5);
      .home-card-img-wrapper {
        flex: 1;
        display: flex;
        justify-content: space-between;
        .home-card-img-item {
          flex: 1;
          margin: 0 px2rem(10);
          background: #fff;
          font-size: 0;
          .home-card-img {
            width: 100%;
            min-height: px2rem(101);
            box-sizing: border-box;
          }
        }
      }
      .home-card-shelf-wrapper {
        display: flex;
        margin-left: px2rem(8);
        .home-card-shelf {
          font-size: px2rem(10.5);
          color: #fff;

          display: flex;
          align-items: center;
          width: px2rem(12);
          line-height: px2rem(15);
        }
        .arrow {
          font-size: px2rem(14);
          display: flex;
          justify-content: center;
          align-items: center;
          color: #ccc;
        }
      }
    }
  }
}
</style>
<style lang="scss" >
// .home-card-img {
//   .van-image__loading {
//     height: 140%;
//   }
// }
</style>