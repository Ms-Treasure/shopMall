<template>
    <div id="tab-bar">
        <slot></slot>
    </div>

</template>
<script>
export default {
    name:'TabBar'
};
</script>
<style scope>
   #tab-bar {
      display: flex;
      position: fixed;
      left: 0;
      right: 0;
      bottom: 0;
      background: #f2f2f2;
      height: 49px;
      box-shadow: 0 -2px 1px rgba(100,100,100,.1);
    }
</style>

