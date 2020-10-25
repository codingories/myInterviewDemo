<template>
    <div>
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
      <el-table-column :label="hoverOption.label">
        <template slot-scope="scope">
          <el-popover trigger="hover" placement="bottom">
            <p>{{ scope.row.productName }}</p>
            <div slot="reference" class="name-wrapper">
              <span size="medium">{{ scope.row.productName }}</span>
            </div>
          </el-popover>
        </template>
      </el-table-column>
        <el-table-column
            prop="deal"
            :label="iconOptions.label">
          <template slot-scope="scope">
            <div>
              <i :class="item.type" v-for="(item,i) in iconOptions.options" :key="i" @click="handleIcon(item.type, scope.row)"></i>
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
      hoverOption: {
        type: Object,
        default: ()=>{ return {} }
      },
      iconOptions: {
        type: Object,
        default: ()=>{ return {} }
      }
    },
      data(){
          return {

          }
      },
      methods:{
        handleIcon(className,row){
          this.$emit('update:handleIcon', {'className':className, 'row':row})
        }
      }
  }
</script>
<style>

</style>
