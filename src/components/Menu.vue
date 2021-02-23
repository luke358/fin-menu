<template>
  <div class="menu-tree">
    <!-- 循环全部数据 -->
    <label v-for="list in dataList" :key="list.id">
      <!-- 判断是否有孩子 -->
      <el-submenu :index="list.id" v-if="list.child">
        <template slot="title">
          <i class="el-icon-location" v-if="list.level"></i>
          <span>{{list.name}}</span>
        </template>
        <label>
          <!-- 递归： 调用自己 把自己的孩子传入 -->
          <child-menu :dataList="list.child"></child-menu>
        </label>
      </el-submenu>
      <!-- 没有孩子则不需要使用 el-submenu -->
      <el-menu-item v-else :index="list.index">
        <span slot="title">{{list.name}}</span>
      </el-menu-item>
    </label>
  </div>
</template>
 
<script>
export default {
  name: 'childMenu',
  props: ['dataList']
}
</script>