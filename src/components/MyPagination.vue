<template>
    <div>
      <div class="block">
        <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :current-page="pageObj.size"
            :page-sizes="[10, 20, 30]"
            :page-size="pageObj.size"
            layout="total, sizes, prev, pager, next, jumper"
            :total="totalPage">
        </el-pagination>
      </div>
    </div>
</template>
<script>
  export default {
    name: 'MyPagination',
    props: {
      pageObj: {
        type: Object,
        default: ()=>{
          return {
            page: 1,
            size: 10
          }
        }
      },
      totalPage: {
        type: Number,
        default: 100
      }
    },
      data(){
          return {

          }
      },
      methods:{
        handleSizeChange(val){
          this.pageObj.size = val
        },
        handleCurrentChange(val){
          this.pageObj.page = val
        }
      }
  }
</script>
<style>

</style>
