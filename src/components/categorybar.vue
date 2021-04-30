<template>
    <div id='chart'>
      <apexchart width="500" type="bar" :options="options" :series="series"></apexchart>
    </div>
</template>
<script>
import adminService from "../../service/adminService";
export default {
  name : 'categorybar',
  data: function() {
    return {
      options: {
        chart: {
          id: 'vuechart-example'
        },
        xaxis: {
          categories: ['Accident','Advice','Education','Find friend','Food and home','Handicraft','Housework','Traffic']
        }
      },
      series: [{
        name: 'quest amount',
        data: [30, 40, 45, 50, 49, 60, 70, 91] //จำนวนเควสแต่ละประเภท
      }]
    }
  },
  methods:{
    getdata:async function(){
      let a = await adminService.getcatbar()
      this.series[0].data = a.count
    }
  },
  created(){
    this.getdata()
  }
}

</script>
<style >
#chart {
  max-width: 650px;
  margin: 35px auto;
}
</style>