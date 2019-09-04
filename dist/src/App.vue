<template>
  <div id="app">
    <!-- 外层el-collapse组件 -->
    <!-- 将数据传递给外层组件 -->
    <collapse :list="list"></collapse>
  </div>
</template>
<script>
import collapse from "./components/collapse";
export default {
  data() {
    return {
      list: [
        {
          title: "第一个",
          name: "1",
          child: ["反复南方福马", "开门了吗", "好不好是和工"]
        },
        {
          title: "第二个",
          name: "2",
          child: ["反复南方福马", "开门了吗", "好不好是和工"]
        },
        {
          title: "第三个",
          name: "3",
          child: ["反复南方福马", "开门了吗", "好不好是和工"]
        }
      ]
    };
  },
  components: {
    collapse
  },
  methods: {}
};
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
  list-style: none;
  text-decoration: none;
  box-sizing: border-box;
}
html,
body,
#app {
  width: 100%;
  height: 100%;
  background: #666;
}
.collapse {
  margin-left: 200px;
  margin-top: 200px;
  background: #fff;
  width: 250px;
  border-radius: 3px;
  overflow: hidden;
}
</style>
