<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="isActivie">
      <slot name="tab-icon-active"></slot>
    </div>
    <div v-else>
      <slot name="tab-icon"></slot>
    </div>
    <div :style="activeStyle">
      <slot name="tab-text"></slot>
    </div>
  </div>
</template>
<script>
export default {
  name: "TabBarTtem",
  props: {
    path: String,
    activeColor: {
      type: String,
      default: "red"
    }
  },
  data() {
    return {
      // isActivie: true
    };
  },
  computed: {
    isActivie() {
      return this.$route.path.indexOf(this.path) !== -1;
    },
    activeStyle() {
      return this.isActivie ? { color: this.activeColor } : {};
    }
  },
  methods: {
    itemClick() {
      this.$router.replace(this.path);
    }
  }
};
</script>
<style>
.tab-bar-item {
  flex: 1;
  text-align: center;
  font-size: 14px;
}
.tab-bar-item img {
  width: 24px;
  height: 24px;
  vertical-align: middle;
  margin-top: 3px;
}
.activie {
  color: brown;
}
</style>