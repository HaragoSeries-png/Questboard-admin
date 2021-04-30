<template>
<div>
<div id="daily">
<dailyquest>
</dailyquest>
</div>
<div id="cate">
  <v-card
    class="mt-4 mx-auto"
    max-width="1100"
  >
    <v-sheet
      class="v-sheet--offset mx-auto"
      color="white"
      max-width="calc(100% )"
    >
    <categorybar></categorybar>
    </v-sheet>

    <v-card-text class="pt-0">
      <div class="title font-weight-light mb-2">
        Category quest created bar chart
      </div>
      <div class="subheading font-weight-light grey--text">
        Bar chart that show quest that is created in each categories.
      </div>
      <v-divider class="my-2"></v-divider>
    </v-card-text>
  </v-card>

  <v-card
    class="mt-4 mx-auto"
    max-width="1200"
  >
    <v-sheet
      class="v-sheet--offset mx-auto"
      
      
      max-width="calc(100%)"
    >
    <queststatuscircle></queststatuscircle> 
    </v-sheet>

    <v-card-text class="pt-0">
      <div class="title font-weight-light mb-2">
        Quest status ration
      </div>
      <div class="subheading font-weight-light grey--text">
        This graph shows ration of quest in each status which are pending, waiting and complete
      </div>
      <v-divider class="my-2"></v-divider>
    </v-card-text>
  </v-card>


</div>
</div>




</template>
<script>
import dailyquest from "../components/Dailyquest"
import categorybar from "../components/categorybar"
import queststatuscircle from "../components/queststatuscircle"
export default {
  name : "Dailyquest",
  components : {dailyquest,categorybar,queststatuscircle},
  
 
}

</script>
<style>
#cate{
width: 1250px;
display: -webkit-flex;
display: -moz-flex;
display: -ms-flex;
display: -o-flex;
display: flex;
justify-content: space-between;
align-items: flex-start ;
min-height: 100vh;
margin: 0 auto;
position: relative;
}
</style>

