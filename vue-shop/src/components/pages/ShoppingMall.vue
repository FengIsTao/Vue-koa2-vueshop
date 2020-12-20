<template>
  <div>
<!--    上方框-->
    <div class="search-bar">
      <van-row>
        <van-col span="3">
          <img :src="locationIcon" alt="" width="75%" class="location-icon" />
        </van-col>
        <van-col span="16">
          <input type="text" class="search-input" />
        </van-col>
        <van-col span="5">
          <van-button size="mini">查找</van-button>
        </van-col>
      </van-row>
    </div>
    <!-- 轮播图swiper -->
    <div class="swiper-area">
      <van-swipe :autoplay="1000">
        <van-swipe-item v-for="(banner, index) in bannerPicArray" :key="index">
          <img v-lazy="banner.imageUrl" alt="" width="100%" />
        </van-swipe-item>
      </van-swipe>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "ShoppingMall",
  data() {
    return {
      msg: "Shopping Mall",
      locationIcon: require("../../assets/images/location.png"),
      bannerPicArray: [
        {
          imageUrl:
            "https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3758616094,217032655&fm=26&gp=0.jpg",
        },
        {
          imageUrl:
            "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3073679434,3672685820&fm=15&gp=0.jpg",
        },
        {
          imageUrl:
            "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1868689485,546684325&fm=15&gp=0.jpg",
        },
      ],
      category:[],
    };
  },
  created() {
    axios({
      url:
        "https://www.fastmock.site/mock/b8705b96ec08b291319b0d576019413d/SmileVue/index",
      method: "get",
    })
      .then((response) => {
        console.log(response);
        if(response.status===200){
          this.category=response.data.data.category
        }
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>
<style scope>
.search-bar {
  height: 2.2rem;
  background-color: #e5017d;
  line-height: 2.2rem;
  overflow: hidden;
}
.search-input {
  width: 100%;
  height: 1.3rem;
  border-top: 0;
  border-left: 0;
  border-right: 0;
  border-bottom: 1px solid #fff !important;
  background-color: #e5017d;
  color: #fff;
}
.location-icon {
  padding-top: 0.2rem;
  padding-left: 0.3rem;
}
.swiper-area {
  clear: both;
  max-height: 15rem;
  overflow: hidden;
}
</style>
