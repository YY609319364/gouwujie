<template>
   <Tabbar></Tabbar>
  <router-view/>
</template>
<script>
  import Tabbar from "./components/common/tabbar/Tabbar";
  export default {
    name:'App',
    components:{
      Tabbar
    }
  }
</script>
<style>
@import "assets/css/base.css";
</style>
