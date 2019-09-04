<template>
  <div>
      <!-- 内层组件通过传递过来的数据进行渲染 -->
    <div class="el-item">
        <!-- 点击修改变量并且打印对应的name值 -->
      <h4 @click="bm">
       {{content.title}}
       <!-- 通过变量控制箭头的旋转 -->
        <span :style="{transform:iszk?'rotate(180deg)':'rotate(0deg)'}">∨</span>
      </h4>
      <!-- 通过一个变量控制列表的展开与收缩 -->
      <div class="con" :style="{height:iszk?'100px':0}" @mouseleave="lea" :name="content.name">
        <p v-for="(item,index) in content.child" 
        :key="index" 
        @mouseover="colo(index)"
        :style="{background:index==curindex?'#ccc':'#000'}"
        >{{item}}</p>
         <!-- 列表高亮显示 -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["content"],
  data() {
    return {
      iszk: false,
      curindex:-1
    };
  },
  methods: {
    bm() {
      this.iszk = !this.iszk;
      console.log(this.content.name)
    },
    colo(index){
        this.curindex=index
    },
    lea(){
        this.curindex=-1;
    }
  }
};
</script>

<style lang="scss" scoped>
span {
  font-size: 20px;
  font-weight: bold;
}

.el-item {
  display: flex;
  flex-direction: column;
  cursor: pointer;
  width: 100%;
  h4 {
    width: 100%;
    position: relative;
    border-bottom: 1px solid #ccc;
    padding: 5px;
    background: #fff;
    span {
      text-align: right;
      transition: 1s;
      position: absolute;
      right: 10px;
    }
  }
  .con {
    background: #000;
    transition: 1s;
    display: flex;
    flex-direction: column;
    p {
      padding: 5px;
      flex: 1;
      border-bottom: 1px solid #eee;
      color: #fff;
    }
  }
}
</style>