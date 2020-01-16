<template>
  <div id="tar-bar">
   <slot></slot>
  </div>
</template>

<script type="text/ecmascript-6">
  export  default {
    name:'TabBar'
  }
</script>

<style  scoped>
  #tar-bar {
    display: flex;
    background-color: #f6f6f6;
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    box-shadow: 0 -1px 2px rgba(0,0,0,0.2);
    font-size: 13px;
  }

</style>
