<template>
  <div class="stuff">
    <div class="clearfix">
      <div class="raw-item" v-for="(item, index) in value" :key="index">
        <el-input v-model="item.name" placeholder="请输入内容" style="width: 200px" ></el-input>
        <el-input v-model="item.specs" placeholder="请输入内容" style="width: 100px"></el-input>
        <i class="delete-icon el-icon-close" v-show="value.length !== 1" @click="remove(index)" ></i>
      </div>
    </div>
    <el-button
      class="eaeaea"
      type="primary"
      size="medium"
      icon="el-icon-plus"
      @click="add"
      >增加一项</el-button
    >
  </div>
</template>
<script>
export default {
  props: {
    value: {
      type: Array,
      default: () => [],
    },
  },
  data(){
    return{}
  },
  methods: {
    add() {
      this.$emit("input", [...this.value, { name: "", specs: "" }]);
    },
    remove(index) {
      const newValue = this.value.filter((item, i) => {
        return i !== index;
      });
      this.$emit("input", newValue);
    },
  },
};
</script>
 
<style lang="stylus">
.delete-icon
  background-color #ccc
  border-radius 50%
  color #fff
  :hover
    background: #ff3232;
    color: #fff;
.raw-item
  float left
  margin-right 65px
  margin-bottom 20px
  .el-input
    margin-right 5px
</style>

