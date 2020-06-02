<template>
  <div class="search-bar">
    <div class="search-bar-wrapper">
      <van-icon class="search" name="search" color="#BBBBBB"></van-icon>
      <input class="search-bar-input" placeholder="搜索" v-model="searchWord" @input="onChange" />
      <van-icon
        class="clear"
        name="clear"
        color="#BBBBBB"
        @click="onClearClick"
        v-if="searchWord.length>0"
      ></van-icon>
    </div>
  </div>
</template>
 
<script>
export default {
  name: "SearchBar",

  data() {
    return {
      searchWord: ""
    };
  },
  methods: {
    onClearClick() {
      this.searchWord = "";
    },
    onChange() {}
  }
};
</script>
 
<style lang="scss" scoped>
@import "../../assets/styles/global";
.search-bar {
  margin-top: px2rem(15);
  padding: 0 px2rem(15);
  .search-bar-wrapper {
    display: flex;
    background: #f5f7f9;
    border-radius: px2rem(40);
    height: px2rem(40);
    padding: 0 px2rem(16);
    box-sizing: border-box;
    .search-bar-input {
      flex: 1;
      font-size: px2rem(15);
      margin: 0px px2rem(8);
      border: none;
      background: transparent;
      color: #333;
      &::placeholder {
        color: #adb4be;
      }
    }
    .search {
      font-size: px2rem(20);
    }
    .clear {
      font-size: px2rem(18);
    }
    .search,
    .clear {
      display: flex;
      align-items: center;
    }
  }
}
</style>