<template>
  <el-menu :default-active="'1'" class="el-menu-demo" mode="horizontal" :unique-opened='true'>
    <el-menu-item index="1">
      <router-link class="nav-link" :to="{path:'/'}">首页</router-link>
    </el-menu-item>
    <el-menu-item index="2">
      <router-link class="nav-link"  :to="{name:'recipe',query:{'classify':'1-1'}}">菜谱大全</router-link>
    </el-menu-item>
  </el-menu>
</template>
<script>
export default {
  name: 'menus'
}
</script>
<style lang="stylus">
  .nav-link {
    display inline-block
  }
</style>


