<template>

    <div>
      {{tableProps}}
      <hr>
      {{tableData}}
      <el-table
          :data="tableData"
          style="width: 100%">
        <el-table-column
            v-for="(item,i) in tableProps"
            :key="i"
            :prop="item.prop"
            :label="item.label"
            :width="item.width?item.width:'140px'"
        />


        <!--        <el-table-column-->
<!--            prop="ID"-->
<!--            label="ID"-->
<!--            width="180">-->
<!--        </el-table-column>-->
<!--        <el-table-column-->
<!--            prop="kind"-->
<!--            label="品类">-->
<!--        </el-table-column>-->
<!--        <el-table-column-->
<!--            prop="type"-->
<!--            label="型号">-->
<!--        </el-table-column>-->
<!--        <el-table-column-->
<!--            prop="usage"-->
<!--            label="功能入口">-->
<!--        </el-table-column>-->
<!--        <el-table-column-->
<!--            prop="productName"-->
<!--            label="产品名称"-->
<!--            width="180">-->


      <el-table-column>
            <template slot-scope="scope">
              <el-popover trigger="hover" placement="bottom">
                <p>{{ scope.row.productName }}</p>
                <div slot="reference" class="name-wrapper">
                  <span size="medium">{{ scope.row.productName }}</span>
                </div>
              </el-popover>
            </template>
      </el-table-column>
<!--        <template slot-scope="scope">-->
<!--          <el-popover trigger="hover" placement="bottom">-->
<!--            <p>{{ scope.row.productName }}</p>-->
<!--            <div slot="reference" class="name-wrapper">-->
<!--              <span size="medium">{{ scope.row.productName }}</span>-->
<!--            </div>-->
<!--          </el-popover>-->
<!--        </template>-->


        <el-table-column
            prop="deal"
            label="操作">
          <template slot-scope="scope">
            <div>
              <i class="el-icon-edit"></i>
              <i class="el-icon-share"></i>
              <i class="el-icon-delete"></i>
            </div>
          </template>
        </el-table-column>
      </el-table>
    </div>
</template>
<script>
  export default {
    name: 'MyTable',
    props: {
      tableProps: {
        type: Array,
        default: () => { return [] }
      },
      tableData: {
        type: Array,
        default: () => { return [] }
      },
    },
      data(){
          return {

          }
      },

  }
</script>
<style>

</style>
