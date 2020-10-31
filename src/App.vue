<template>
  <div id="app">
    {{input}}
    <el-input v-model="input" placeholder="请输入内容" type="textarea"></el-input>
    <el-button type="primary" @click="confirm">确认</el-button>
    <h4>{{result}}</h4>
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
      input: '',
      result:'',
      hotelPeopleMap: {"JW": 400,"Golden":450,"Deltas":600,"PeaceExpress":700}
    }
  },
  components: {

  },
  methods: {
    confirm(){
      // this.validOne(this.input)

      // const tempArray = ['CNN JW 2019-4-1 2019-5-1 10', 'ABC Golden 2019-3-11 2019-4-1 5']
      // tempArray.forEach(v=>{
      //   console.log(v)
      //   console.log(this.validOne(v))
      // })


      let tempList = ['CNN JW 2019-4-1 2019-5-1 399',
      'TW JW 2019-4-2 2019-5-2 1']
      this.validTwo(tempList)

    },
    validOne(arg){
      let tempList = arg.split(' ')
      let tempStr = tempList[1] + ' ' + tempList[0] + ' ' + tempList[4]
      if(this.hotelPeopleMap[tempList[1]]<tempList[4]){
        return  "invilid"
      }else{
        return tempStr
      }
    },
    validTwo(arg){
      let firstInfo = arg[0].split(' ')
      let secondInfo = arg[1].split(' ')
      if(firstInfo[1] === secondInfo[1]){
        console.log('旅馆相同')
        if(this.isDateIntersection(firstInfo[2],firstInfo[3],secondInfo[2],secondInfo[3])) {
          console.log('有日期重叠')
          let totalDays = parseInt(firstInfo[4])+parseInt(secondInfo[4])
          let hotelDays = this.hotelPeopleMap[firstInfo[1]]
          if(totalDays>hotelDays){
            console.log('invalid')
          }else{
            this.consoleTwoInfo(arg)
          }
        } else{
          this.consoleTwoInfo(arg)
        }
      }
    },
    consoleTwoInfo(arg){
      arg.map(v=>{
        console.log(this.validOne(v))
      })
    },
    //判断两个时间是否有交集
    isDateIntersection(start1, end1, start2, end2) {
      var startdate1 = new Date(start1.replace("-", "/").replace("-", "/"));
      var enddate1 = new Date(end1.replace("-", "/").replace("-", "/"));

      var startdate2 = new Date(start2.replace("-", "/").replace("-", "/"));
      var enddate2 = new Date(end2.replace("-", "/").replace("-", "/"));

      if (startdate1 >= startdate2 && startdate1 <= enddate2) {

        return true;
      }

      if (enddate1 >= startdate2 && enddate1 <= enddate2) {
        return true;
      }

      if (startdate1 <= startdate2 && enddate1 >= enddate2) {
        return true;
      }
      return false;
    }


  },
  watch: {

  }

}
</script>

<style>

</style>
