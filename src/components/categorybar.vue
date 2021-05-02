<template>
    <div id='chart'>
      <apexchart width="575" type="bar" :options="options" :series="series"></apexchart>
    </div>
</template>
<script>
import adminService from "../../service/adminService";
export default {
  name : 'categorybar',
  data: function() {
    return {
      options: {
        
        xaxis: {
          categories: ['Accident','Advice','Education','Find friend','Food and home','Handicraft','Housework','Traffic']
        }
      },
      series: [10,20,30,40,50,60,70,50],
      
    }
  },
  methods:{
    getdata:async function(){
      
      let a = await adminService.getcatbar()
      // console.log('a '+JSON.stringify(a.count))
      let newdata = a.map((ac)=>{
        return ac.count
      })
      let newaxis = a.map(ac=>{
        // console.log(ac._id)
        return ac._id
      })
      
      this.series= [{data:newdata}]
      // console.log(newaxis)
      this.options = {xaxis:{categories:newaxis}}
           
    }
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