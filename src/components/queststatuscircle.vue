<template>
    <div id = 'chart'>
      <apexchart width="510" type="donut" :options="options" :series="series"></apexchart>
    </div>
</template>
<script>
export default {
  name : 'queststatuscircle',
  data: function() {
    return {
      options: {
      labels: ['pending','waiting','complete']
      },
      series: [30,30,30] //จำนวนของเควสแต่ละสถานะ
      
    }
    
  }
}
</script>
<style >
#chart {
  margin-top: 50px;
}
</style>