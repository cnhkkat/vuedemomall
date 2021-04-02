<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banner="banner"></home-swiper>
    <recommend-view :recommend="recommend"></recommend-view>
    <feature></feature>


  </div>
</template>

<script>
import NavBar from "../../components/common/navbar/NavBar";
import HomeSwiper from './childComps/HomeSwiper';
import RecommendView from './childComps/RecommendView';
import Feature from './childComps/Feature'
import { getHomeMultidata } from "../../network/home";


export default {
  name: "Home",
  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    Feature
  },
  data() {
    return {
      // result:null
      banner:[],
      recommend:[]
    }
  },
  created() {
    getHomeMultidata().then(res => {
      // console.log(res);
      // this.result=res
      this.banner=res.data.banner.list
      this.recommend=res.data.recommend.list
    })
  },
};
</script>

<style scoped>
#home {
  padding-top: 44px;
  padding-bottom: 40px;
}
.home-nav {
  background-color: var(--color-tint);
  color: white;

  position: fixed;
  left: 0;
  right: 0;
  top: 0;

  z-index: 9;
}
</style>