<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"/>
    <recommend :recommends="recommends"/>
    <feature-view/>
    <tab-control :titles='["流行","新款","精选"]' class="tab-control"/>
  </div>
</template>
<script>
import NavBar from "components/common/navbar/NavBar";
import TabControl from "components/content/tabControl/TabControl";

import HomeSwiper from "./childComps/HomeSwiper";
import Recommend from "./childComps/Recommend";
import FeatureView from "./childComps/FeatureView";

import { getHomeMultidata } from "network/home.js";

export default {
  name: "Home",
  components: {
    NavBar,
    TabControl,
    HomeSwiper,
    Recommend,
    FeatureView
  },
  data() {
    return {
      banners: [],
      recommends: [],
      goods: {
        'pop': { page: 0, list: [] },
        'news': { page: 0, list: [] },
        'sell': { page: 0, list: [] }
      }
    };
  },
  created() {
    getHomeMultidata().then(res => {
      this.banners = res.data.data.banner.list;
      this.recommends = res.data.data.recommend.list;
    });
  }
};
</script>
<style scope>
#home {
  padding-top: 44px;
}
.home-nav {
  background: var(--color-tint);
  color: #fff;
  position: fixed;
  z-index: 9;
  left: 0;
  right: 0;
  top: 0;
}
.tab-control {
  position: sticky;
  top: 44px;
}
</style>