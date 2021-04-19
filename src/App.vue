<template>
  <router-view />
</template>
<script lang='ts'>
import { ref, provide } from "vue";
import { router } from "./router";
export default {
  name: "App",
  setup() {
    const width = document.documentElement.clientWidth; //获取屏幕宽度
    const menuVisible = ref(width >= 500 ? true : false);
    provide("menuVisible", menuVisible); //set
    router.afterEach(() => {
      //路由切换后执行的钩子
       if (width <= 500) {
        menuVisible.value = false;
      }
      console.log("路由切换了");
    });
  },
};
</script>