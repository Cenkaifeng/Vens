<template>
  <view class="Cart">
      {{ "It's Cart page" }}
  </view>
</template>

<script>
import { reactive, toRefs } from 'vue';
export default {
  name: 'shopingCart',
  components: {
    
  },
  setup(){
    const state = reactive({
    });

    return {
      ...toRefs(state)
    }
  }
}
</script>

<style lang="scss">
.cart {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
