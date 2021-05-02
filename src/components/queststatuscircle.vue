<template>
    <div id = 'chart'>
      <apexchart width="510" type="donut" :options="options" :series="series"></apexchart>
    </div>
</template>
<script>
import adminService from "../../service/adminService";
export default {
  name : 'queststatuscircle',
  data: function() {
    return {
      options: {
        labels: ['pending','waiting','complete']
      },
      series: [30,30,30] //จำนวนของเควสแต่ละสถานะ
      
    }
    
  },
  methods:{
    getdata:async function(){
      let a = await adminService.getcir()
      // console.log('a '+JSON.stringify(a.count))
      let newdata = a.map((ac)=>{
        return ac.count
      })
      let newaxis = a.map(ac=>{
        // console.log(ac._id)
        return ac._id
      })
      
      this.series= newdata
      // console.log(newaxis)
      this.options = {labels:newaxis}
    },  
  },
  created(){
    this.getdata()
  }
}
</script>
<style >
#chart {
  margin-top: 50px;
}
</style>