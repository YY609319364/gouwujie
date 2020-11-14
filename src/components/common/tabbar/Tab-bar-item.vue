<template>
  <div class="tab-bar-item" @click="itemClick">
    <slot v-if="!isActived" name="slot-img"></slot>
    <slot v-else name="slot-active-img"></slot>
    <div :style="activeStyle">
      <slot name="slot-text"></slot>
    </div>

  </div>
</template>

<script>
  export default {
    name: "tab-bar-item",
    data(){
      return{
       // isActived:false
      }
    },
    computed:{
      isActived(){
        return this.$route.path.indexOf(this.path)!==-1
      },
      activeStyle(){
        return this.isActived?{color:this.activeColor}:{}
      }
    },
    props:{
      path:String,
      activeColor:{
        type:String,
        default:'skyblue'
      }
    },
    methods:{
      itemClick(){
        this.$router.push(this.path)
      }
    }
  }
</script>

<style scoped>
  .tab-bar-item {
    text-align: center;
    height: 49px;
  }
</style>