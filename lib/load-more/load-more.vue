<template>
  <view class="load-more" @click="_onClick">
    <text :class="{ more: !more }">{{ more ? "加载更多" : "没有更多了" }}</text>
  </view>
</template>

<script>
export default {
  name: "load-more",
  props: {
    more: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    _onClick() {
      if (this.more === false) {
        return;
      }

      this.$emit("onClick");
    }
  }
};
</script>

<style lang="scss">
$active-color: #488ee9;

.load-more {
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 50px;
  font-size: 16px;
  color: $active-color;
}

.more {
  color: #808080;
}
</style>
