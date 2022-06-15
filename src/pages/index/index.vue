<template>
  <view class="index">
    <view>
      <img src="" alt="" />
    </view>
    {{ msg }}
    <view class="btn">
      <nut-button type="primary" @click="handleClick('text', msg2, true)">点我</nut-button>
    </view>
    <!-- <nut-toast :msg="msg" v-model:visible="show" :type="type" :cover="cover" /> -->
    <view class="content-box">
      <Cart/>
    </view>
    <nut-tabbar @tab-switch="tabSwitch">
      <nut-tabbar-item tab-title="首页" icon="home"></nut-tabbar-item>
      <nut-tabbar-item tab-title="分类" icon="category"></nut-tabbar-item>
      <nut-tabbar-item tab-title="购物车" icon="cart"></nut-tabbar-item>
      <nut-tabbar-item tab-title="我的" icon="my"></nut-tabbar-item>
    </nut-tabbar>
  </view>
</template>

<script>
import { reactive, toRefs } from "vue";
import { Tabbar, TabbarItem } from "@nutui/nutui-taro";
import home from "../../components/homePage.vue";
import mine from "../../components/myCentor.vue";
import shopingCart from "../../components/shopingCart.vue";
export default {
  name: "Index",
  components: {
    "nut-tabbar": Tabbar,
    "nut-tabbar-item": TabbarItem,
    // 'Home': home,
    'Cart': shopingCart, 
    // 'Mine': mine
  },
  setup() {
    const state = reactive({
      msg: "欢迎使用 NutUI3.0 开发小程序",
      msg2: "你成功了～",
      type: "text",
      index: 0,
      show: false,
      cover: false,
    });

    const handleClick = (type, msg, cover = false) => {
      state.show = true;
      state.msg2 = msg;
      state.type = type;
      state.cover = cover;
      wx.navigateTo({
        url: "/pages/demo/demo",
      });
    };

    const tabSwitch = (item, index) => {
      console.log(item, index);
      state.index = index;
    };

    return {
      ...toRefs(state),
      tabSwitch,
      handleClick,
    };
  },
};
</script>

<style lang="scss">
.index {
  height: 100%;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  .nut-tabbar {
    position: absolute;
    bottom: 0;
  }
}
</style>
