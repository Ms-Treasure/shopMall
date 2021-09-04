<template>
     <tab-bar>
      <tab-bar-item path="/home" activeColor="#fd6a86">
        <img slot="tab-icon-active" src="~assets/img/tabbar/home_active.svg" alt="">
        <img slot="tab-icon" src="~assets/img/tabbar/home.svg" alt="">
        <div slot="tab-text" >首页</div>
      </tab-bar-item>
      <tab-bar-item  path="/category" activeColor="#fd6a86">
        <img slot="tab-icon-active" src="~assets/img/tabbar/category_active.svg" alt="">
        <img slot="tab-icon" src="~assets/img/tabbar/category.svg" alt="">
        <div slot="tab-text" >分类</div>
      </tab-bar-item>
      <tab-bar-item path="/cart" activeColor="#fd6a86">
        <img slot="tab-icon-active" src="~assets/img/tabbar/shopcart_active.svg" alt="">
        <img slot="tab-icon" src="~assets/img/tabbar/shopcart.svg" alt="">
        <div slot="tab-text" >购物车</div>
      </tab-bar-item>
      <tab-bar-item path="/profile" activeColor="#fd6a86">
        <img slot="tab-icon-active" src="~assets/img/tabbar/profile_active.svg" alt="">
        <img slot="tab-icon" src="~assets/img/tabbar/profile.svg" alt="">
        <div slot="tab-text" >我的12</div>
      </tab-bar-item>
    </tab-bar>
</template>
<script>

import TabBar from 'components/common/tabbar/TabBar';
import TabBarItem from 'components/common/tabbar/TabBarItem'
export default {
    name: 'MainTabBar',
    components: {
    TabBar,
    TabBarItem
  }
}
</script>
<style scope>
    
</style>