<template>
    <div>
    <v-card
    class="mt-4 mx-auto"
    max-width="1200"
  >
    <v-sheet
      class="v-sheet--offset mx-auto"
      color="cyan"
      elevation="12"
      max-width="calc(100% - 32px)"
    >
      <v-sparkline
        :labels="labels"
        :value="value"
        color="white"
        line-width="2"
        padding="16"
      ></v-sparkline>
    </v-sheet>

    <v-card-text class="pt-0">
      <div class="title font-weight-light mb-2">
        Quest created
      </div>
      <div class="subheading font-weight-light grey--text">
        Daily quest created
      </div>
      <v-divider class="my-2"></v-divider>
    </v-card-text>
  </v-card>
</div>
</template>
<script>
export default {
    data: () => ({
      labels: [
        'monday',
        'tuesday',
        'wednesday',
        

      ],
      value: [
        20,
        50,
        60,
        70,
      ], //จำนวนเควสที่ถูกสร้างในแต่ละวัน
    }),
  }
</script>
<style>
.v-sheet--offset {
    top: -24px;
    position: relative;
  }
</style>
