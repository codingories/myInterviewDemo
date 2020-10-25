<template>
    <div>
      <el-form :inline="true">
        <el-dropdown>
          <el-button type="primary">
            {{myFormData.title}}<i class="el-icon-arrow-down el-icon--right"></i>
          </el-button>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item v-for="item in myFormData.content" :key="item.index">{{item.name}}</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
        <el-form-item class="searchStyle">
          <el-input
              placeholder="请输入内容"
              prefix-icon="el-icon-search"
              label-width="500px"
              v-model="input2">
          </el-input>
        </el-form-item>
      </el-form>
    </div>
</template>
<script lang="js">
export default {
  name: "myForm",
  data(){
    return {
      input2: '',
    }
  },
  props: {
    myFormData: {
      type: Object,
      default:{
        title: "全部种类",
        content: [{index:1,name:"下拉一"},{index:2,name:"下拉二"},{index:3,name:"下拉三"}]
      },
    }
  }
}
</script>
<style lang="scss" scoped>

</style>
