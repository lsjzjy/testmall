<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon" ></slot></div>
    <div v-else><slot name="item-icon-active" ></slot></div>
    <div :style="isColorActive"> <slot name="item-text"></slot></div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    name: 'TabBarItem',
    props:{
      path:String,
      isActiveColor:{
        type:String,
        default:'red'
      }
    },
    data(){
      return{
        // isActive:true
      }
    },
    computed:{
      isActive(){
        return this.$route.path.indexOf(this.path) !==-1;
        },
      isColorActive(){
        return this.isActive ? {color:this.isActiveColor}:{}
      }
    },
    methods:{
      itemClick(){
       this.$router.replace(this.path)
      }
    }
  }
</script>

<style scoped>
  .tab-bar-item {
    flex: 1;
    text-align: center;
    height: 49px;
  }
  .tab-bar-item img {
    margin-top: 3px;
    width: 24px;
    height: 24px;
    vertical-align: middle;
    margin-bottom: 2px;
  }
</style>
