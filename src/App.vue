<template>
  <div id="app">
    <div class="nav-list-container">
      <nav-list :data="navListData"></nav-list>
    </div>
    <router-view></router-view>
  </div>
</template>
<script>
import NavList from '@/components/NavList';
import { navListData } from '@/util/baseData';
export default {
  name: 'app',
  components: {
    NavList
  },
  data() {
    return {
      navListData: navListData
    }
  }
}
</script>
<style lang="less">
#app {
}
</style>
