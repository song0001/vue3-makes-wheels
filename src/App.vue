<template>
  <router-view />
</template>
<script lang='ts'>
import { ref, provide } from "vue";
export default {
  name: "App",
  setup() {
    const width = document.documentElement.clientWidth;//获取屏幕宽度
    const menuVisible = ref(width >= 500 ? true : false);
    provide("menuVisible", menuVisible); //set
  },
};
</script>