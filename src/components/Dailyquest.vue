<template>
<div>
  <apexchart type="line" height="350" :options="chartOptions" :series="series"></apexchart>
</div>
   
</template>
<script>
import adminService from "../../service/adminService";

export default {
    data: function() {
      return {
        series: [{
              data: [10, 41, 35, 51, 49, 62, 69, 91, 148]
          }],
        chartOptions: {
          chart: {
              height: 350,
              type: 'line',
              zoom: {
              enabled: false
              }
              },
          dataLabels: {
              enabled: false,
              style: {
                color: "#E91E63"
              }
            },
          stroke: {
              curve: 'straight'
            },
          grid: {
              row: {
                colors: ['#f3f3f3', 'transparent'], // takes an array which will be repeated on columns
                opacity: 0.5
              },
            },
          xaxis: {
              categories: ['',''],
            }
        }
      }
    },
    methods:{
      getdata:async function(){
      let a = await adminService.getdaily()
      // console.log('a '+JSON.stringify(a.qcount))
      a = bouncer(a)
      console.log('b '+JSON.stringify(a))
      let newdata = a.map((ac)=>{
        return ac.qcount
      })
      let newaxis = a.map(ac=>{
       console.log(ac.createdAt)
        return ac.createdAt
      })
      function bouncer(arr) {
        return arr.filter(function(item){
          return !!item.createdAt;
        });
      }


      newaxis 
      // newaxis = ['a','b','c','d','e','f','g']
      this.series= [{data:newdata}]
      console.log(newaxis[1] + JSON.stringify(newaxis))
      this.chartOptions = {
        chart: {height: 350,type: 'line',color: "red",zoom: {enabled: false}},
        dataLabels: {enabled: false,style: {color: "#E91E63"}},
        stroke: {curve: 'straight'},
        grid: {row: {colors: ['#f3f3f3', 'transparent'],opacity: 0.5},},
        xaxis: {categories:newaxis}
      }
    }, 
  },
   created(){
      this.getdata()
    }
}
</script>
<style>
.v-sheet--offset {
    top: -24px;
    position: relative;
  }
</style>
