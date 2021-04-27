<template>
    <div id = 'chart'>
      <apexchart width="500" type="donut" :options="options" :series="series"></apexchart>
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
  max-width: 650px;
  margin: 35px auto;
}
</style>