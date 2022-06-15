<template>
  <view class="home">
      {{ "It's Home page" }}
  </view>
</template>

<script>
import { reactive, toRefs } from 'vue';
export default {
  name: 'homePage',
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
.home {
  background: #ccc;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
