<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
      <swiper>
        <swiper-item v-for="item in banner" :key="item.index">
            <a :href="item.link">
              <img :src="item.image" alt="">
            </a>
        </swiper-item>
      </swiper>
    </nav-bar>
  </div>
</template>

<script>
import NavBar from "@/components/common/navbar/NavBar";
import { getHomeMultidata } from "@/network/home";
// import Swiper from '../../components/common/swiper'
// import SwiperItem from '../../components/common/swiper/SwiperItem'
import {Swiper,SwiperItem} from '../../components/common/swiper'

export default {
  name: "Home",
  components: {
    NavBar,
    Swiper,
    SwiperItem
  },
  data() {
    return {
      // result:null
      banner:[],
      recommend:[]
    };
  },
  created() {
    getHomeMultidata().then((res) => {
      // console.log(res);
      // this.result=res
      this.banner=res.data.banner.list
      this.recommend=res.data.recommend.list
    });
  },
};
</script>

<style scoped>
.home-nav {
  background-color: var(--color-tint);
  color: white;
}
</style>