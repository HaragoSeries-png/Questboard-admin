<template>
    <div id='chart'>
    </div>
</template>
<script>
var options = {
  chart: {
    type: 'bar'
  },
  series: [{
    name: 'amount',
    data: [20,30,40,50,100]
  }],
  xaxis: {
    categories: ['Handicraft','Advice','Education','Accident','Housework','Find friends','Food and home economics','Traffic']
  }
}
var chart = new ApexCharts(document.querySelector("#chart"), options);

chart.render();
</script>
<style >
#chart {
  max-width: 650px;
  margin: 35px auto;
}
</style>