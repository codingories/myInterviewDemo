<template>
  <div id="app">
    <myForm :myFormData="myFormData"></myForm>
    <my-table :tableProps="tableProps" :tableData="tableData" :hoverOption="hoverOption" :iconOptions="iconOptions" @update:handleIcon="handleIcon"></my-table>
    <my-pagination :total-page="totalPage" :page-obj="pageObj"></my-pagination>
  </div>
</template>

<script>
import MyForm from './components/MyForm'
import MyTable from "./components/MyTable"
import MyPagination from "./components/MyPagination"
export default {
  name: 'App',
  data() {
    return {
      totalPage: 20,
      pageObj: {
        page: 1,
        size: 5
      },
      myFormData: {
        title: "全部种类",
        content: [{index:1,name:"下拉五"},{index:2,name:"下拉二"},{index:3,name:"下拉三"}]
      },
      hoverOption:{
        label: "产品名称",
        content: "",
      },
      iconOptions: {
        label: '操作',
        options: [
          {
            type:"el-icon-edit"
          },
          {
            type:"el-icon-share"
          },
          {
            type:"el-icon-delete"
          },
        ]
      },
      tableProps: [
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
    }
  },
  components: {
    MyPagination,
    MyTable,
    MyForm
  },
  methods: {
    handleIcon(arg){
      console.log(arg)
    }
  },
  watch: {
    pageObj: {
      handler: function (newValue,oldValue) {
        console.log(newValue,oldValue)
      },
      deep: true,
      immediate: true
    }
  }

}
</script>

<style>

</style>
