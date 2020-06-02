<template>
  <div class="banner" v-lazy:background-image="`http://www.youbaobao.xyz/book/res/bg.jpg`">
    <span class="banner-txt">欢迎来到书城，点击进入个人中心</span>
    <van-button class="banner-button" round color="linear-gradient(to right, #4bb0ff, #6149f6)">点击进入</van-button>
  </div>
</template>
 
<script>
export default {};
</script>
 
<style lang="scss" scoped>
@import "../../assets/styles/global";
.banner {
  margin: px2rem(20) px2rem(20) 0 px2rem(20);
  border-radius: px2rem(10);
  min-height: px2rem(125);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .banner-txt {
    font-size: px2rem(18);
    text-align: center;
    color: #fff;
  }
  .banner-button {
    margin-top: px2rem(15);
    width: 40%;
    height: px2rem(38);
  }
}
</style>