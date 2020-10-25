<template>
  <div id="app">
<!--      ID 产品名称 品类 型号 功能入口 操作-->
    <myForm :myFormData="myFormData"></myForm>
    <my-table :tableProps="tableProps" :tableData="tableData"></my-table>

<!--    <div class="block">-->
<!--      <el-pagination-->
<!--          @size-change="handleSizeChange"-->
<!--          @current-change="handleCurrentChange"-->
<!--          :current-page="currentPage4"-->
<!--          :page-sizes="[100, 200, 300, 400]"-->
<!--          :page-size="100"-->
<!--          layout="total, sizes, prev, pager, next, jumper"-->
<!--          :total="400">-->
<!--      </el-pagination>-->
<!--    </div>-->
  </div>
</template>

<script>
import MyForm from '@/components/MyForm'
import MyTable from "./components/MyTable"
export default {
  name: 'App',
  data() {
    return {
      myFormData: {
        title: "全部种类",
        content: [{index:1,name:"下拉五"},{index:2,name:"下拉二"},{index:3,name:"下拉三"}]
      },
      tableProps: [
        // ID 产品名称 品类 型号 功能入口 操作
        {
          prop:"ID",
          label:"产品名称"
        },
        {
          prop:"kind",
          label:"品类"
        },
        {
          prop:"type",
          label:"型号"
        },
        {
          prop:"usage",
          label:"功能入口"
        }
      ],
      tableData: [
        {
        ID: '0098',
        productName: '电压力锅',
        kind: '电压力锅V型',
        type: '家用型001',
        usage: '5',
        deal: '',
      },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
        {
          ID: '0098',
          productName: '电压力锅',
          kind: '电压力锅V型',
          type: '家用型001',
          usage: '5',
          deal: '',
        },
      ],
      currentPage1: 5,
      currentPage2: 5,
      currentPage3: 5,
      currentPage4: 4

    }
  },
  components: {
    MyTable,
    MyForm
  },
  methods: {
    handleSizeChange(val) {
      console.log(`每页 ${val} 条`);
    },
    handleCurrentChange(val) {
      console.log(`当前页: ${val}`);
    }
  },

}
</script>

<style>
  .searchStyle {
    padding-left: 30px;
  }
</style>
