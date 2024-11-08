<script setup>
import {
  HomeFilled
} from '@element-plus/icons-vue'

const menuList = JSON.parse(sessionStorage.getItem('menuList'))
</script>

<template>
  <el-menu
      active-text-color="#A0C1FF"
      background-color="#2D3A4B"
      class="el-menu-vertical-demo"
      text-color="#fff"
      router
      :default-active="'/index'"
  >
    <el-menu-item index="/index">
      <el-icon>
        <home-filled/>
      </el-icon>
      <span>首页</span>
    </el-menu-item>
    <el-sub-menu :index="menu.path" v-for="menu in menuList">
      <template #title>
        <el-icon>
          <svg-icon :icon="menu.icon"/>
        </el-icon>
        <span>{{ menu.name }}</span>
      </template>
      <el-menu-item :index="item.path" v-for="item in menu.children">
        <el-icon>
          <svg-icon :icon="item.icon"/>
        </el-icon>
        <span>{{ item.name }}</span>
      </el-menu-item>
    </el-sub-menu>


  </el-menu>
</template>

<style lang="sass" scoped>

</style>