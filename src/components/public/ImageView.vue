<template>
  <div class="image-view">
    <van-image width="100%" :round="round" :lazy-load="lazyLoad" :src="src">
      <template v-slot:loading>
        <van-loading type="spinner" size="20" />
      </template>
    </van-image>
  </div>
</template>
 
<script>
export default {
  props: {
    round: {
      type: Boolean,
      default: false
    },
    lazyLoad: {
      type: Boolean,
      default: true
    },
    src: {
      type: String,
      default: ""
    }
  },
  data() {
    return {};
  }
};
</script>
 
<style lang="scss" scoped>
@import "../../assets/styles/global";
</style>