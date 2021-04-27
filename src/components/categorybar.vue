<template>
    <div id='chart'>
      <apexchart width="500" type="bar" :options="options" :series="series"></apexchart>
    </div>
</template>
<script>

export default {
  name : 'categorybar',
  data: function() {
    return {
      options: {
        chart: {
          id: 'vuechart-example'
        },
        xaxis: {
          categories: ['Handicraft','Advice','Education','Accident','Housework','Find friend','Food and home','Traffic']
        }
      },
      series: [{
        name: 'quest amount',
        data: [30, 40, 45, 50, 49, 60, 70, 91] //จำนวนเควสแต่ละประเภท
      }]
    }
  }
}

</script>
<style >
#chart {
  max-width: 650px;
  margin: 35px auto;
}
</style>