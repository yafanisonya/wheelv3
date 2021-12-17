<template>
  <div class="topnav">
      <div class="logo">LOGO</div>
      <ul class="menu">
          <li>菜单1</li>
          <li>菜单2</li>
      </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name:'TopNav'
})
</script>

<style lang="scss" scoped>
.topnav{
  display: flex;
  padding:16px;
  background:pink;

  > .logo{
    margin-right:auto;
    max-width:6em;
  }

  > .menu{
    display: flex;
    flex-wrap: nowrap;
    white-space: nowrap;

    > li{
      margin: 0 1em;
    }
  }
}
</style>