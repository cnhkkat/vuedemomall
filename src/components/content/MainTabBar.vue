<template>
  <div id="app">
      <tab-bar>
        <tab-bar-item path="/home" activeColor="blue">
           <img slot="item-icon" src="@/assets/img/tabbar/home1.png" alt="">
           <img slot="item-icon-active" src="@/assets/img/tabbar/home2.png" alt="">
           <div slot="item-text">首页</div>
        </tab-bar-item>
        <tab-bar-item path="/category" activeColor="blue">
          <img slot="item-icon" src="../../assets/img/tabbar/category1.png" alt="">
           <img slot="item-icon-active" src="../../assets/img/tabbar/category2.png" alt="">
           <div slot="item-text">分类</div>
        </tab-bar-item>
        <tab-bar-item path="/cart" activeColor="blue">
          <img slot="item-icon" src="../../assets/img/tabbar/shopcart1.png" alt="">
           <img slot="item-icon-active" src="../../assets/img/tabbar/shopcart2.png" alt="">
           <div slot="item-text">购物车</div>
        </tab-bar-item>
        <tab-bar-item path="/profile" activeColor="blue">
          <img slot="item-icon" src="../../assets/img/tabbar/profile1.png" alt="">
           <img slot="item-icon-active" src="../../assets/img/tabbar/profile2.png" alt="">
           <div slot="item-text">我的</div>
        </tab-bar-item>
    </tab-bar> 
  </div>
</template>

<script>
import TabBar from '../common/tabbar/TabBar'
import TabBarItem from '../common/tabbar/TabBarItem'

export default {
  name:"MainTabBar",
   components: {
    TabBar,
    TabBarItem
  }
}
</script>
