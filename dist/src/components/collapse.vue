<template>
  <div class="collapse">
      <!-- 菜单title为手风琴菜单的title -->
    <div v-for="(item,index) in list" :key="index" :title="item.title">
        <!-- 内层el-collapse-item组件 -->
      <Item :content="item"></Item>
      <!-- 给内层组件传递数据 -->
    </div>
  </div>
</template>

<script>
import Item from "./Item.vue";
export default {
    props:["list"],
    components:{
        Item
    }
};
</script>

<style>
</style>