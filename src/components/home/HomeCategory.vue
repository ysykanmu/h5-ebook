<template>
  <div class="home-category">
    <div class="home-category-header">{{title}}</div>
    <div class="home-category-content">
      <div class="home-category-items" v-for="(item,index) of categoryData" :key="index">
        <div class="home-category-item">
          <div class="home-category-info">
            <div class="book-category">{{item.text}}</div>
            <div class="book-num">{{item.num}}本书</div>
          </div>
          <div class="home-category-imgs">
            <van-image class="home-category-img1" :lazy-load="true" :src="item.cover">
              <template v-slot:loading>
                <van-loading type="spinner" size="20" />
              </template>
            </van-image>
            <van-image class="home-category-img2" :lazy-load="true" :src="item.cover2">
              <template v-slot:loading>
                <van-loading type="spinner" size="20" />
              </template>
            </van-image>
          </div>
        </div>
      </div>
    </div>

    <div class="home-category-footer">
      <van-button round block class="home-category-btn">{{btnText}}</van-button>
    </div>
  </div>
</template>
 
<script>
export default {
  props: {
    title: String,
    data: Array,
    btnText: {
      type: String,
      default: "换一批"
    }
  },
  data() {
    return {
      CATEGORY: {
        computerscience: "计算机科学",
        socialsciences: "社会科学",
        economics: "经济学",
        education: "教育学",
        engineering: "工程学",
        environment: "环境学",
        geography: "地理学",
        history: "历史学",
        laws: "法学",
        lifesciences: "生命科学",
        literature: "文学",
        biomedicine: "生物医学",
        businessandmanagement: "工商管理",
        earthsciences: "地球科学",
        materialsscience: "材料科学",
        mathematics: "数学",
        medicineandpublichealth: "公共卫生",
        philosophy: "哲学",
        physics: "物理",
        politicalscienceandinternationalrelations: "国际关系",
        psychology: "心理学",
        statistics: "统计学"
      }
    };
  },
  computed: {
    categoryData() {
      const _categoryData = this.data.slice(0, 6);
      _categoryData.forEach(book => {
        book.text = this.CATEGORY[book.categoryText.toLowerCase()];
      });
      return _categoryData;
    }
  }
};
</script>
 
<style lang="scss" scoped>
@import "../../assets/styles/global";
.home-category {
  padding: px2rem(16) px2rem(14) px2rem(20) px2rem(14);
  .home-category-header {
    font-size: px2rem(21);
    font-weight: bold;
    padding-left: px2rem(10);
  }
  .home-category-content {
    margin-top: px2rem(18);
    display: flex;
    flex-wrap: wrap;
    .home-category-items {
      box-sizing: border-box;
      padding: px2rem(6);
      flex: 0 0 50%;
      .home-category-item {
        display: flex;
        background: #f8f9fb;
        .home-category-info {
          flex: 0 0 62.5%;
          padding: px2rem(13.5) px2rem(0) px2rem(14.5) px2rem(16);
          box-sizing: border-box;
          .book-category {
            font-size: px2rem(16);
            font-weight: bold;
          }
          .book-num {
            margin-top: px2rem(30);
            font-size: px2rem(12);
            color: #868686;
          }
        }
        .home-category-imgs {
          flex: 0 0 37.5%;
          position: relative;
          .home-category-img1 {
            position: absolute;
            bottom: 0;
            right: 0;
            width: px2rem(48);
            z-index: 2;
          }
          .home-category-img2 {
            position: absolute;
            bottom: 0;
            right: px2rem(30);
            width: px2rem(36);
          }
        }
      }
    }
  }
  .home-category-footer {
    margin-top: px2rem(20);
    padding: 0 px2rem(10);
    .home-category-btn {
      color: #3696ef;
      font-size: px2rem(14);
    }
  }
}
</style>