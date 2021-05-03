<template>
  <div>
      <h1>
          Report page
      </h1>
      
    <v-card v-for="report in reports" :key="report._id" class="card"
      color="#26c6da"
      height="300"
      style="width:300;height:300"
    > 
      <v-card-text  class="sender">
       Sender: {{report.sender}}
      </v-card-text>
      <v-card-actions>
        <v-list-item>
          <v-list-item-content  class="card-content">
            <v-card-textarea class="card-text">Detail: {{report.message}} </v-card-textarea>
          </v-list-item-content>
        </v-list-item>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
import adminService from "../../service/adminService";
export default {
    name:"report",
    methods:{
        async getdata(){
            let a = await adminService.getreport()
            this.reports = a.log
        }
    },
    data:function(){
        return{
            reports:[]
        }      
    },
    created(){
        this.getdata()
    }
    
}
</script>

<style>
.card{
    margin-top:5%;
    width: 600px;
    height:250px;
    border: 1px solid black;
}
.card-content{
    line-height: 1.5;
    font-size: 0.9em;
    padding: 15px;
    border-top: 2px solid #333333;
    border-right: 2px solid #333333;
    border-left: 2px solid #333333;
    border-bottom: 2px solid #333333;
}
.card-text{
  overflow: auto;
}
.sender{
  padding: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #555555;
    background: #eeeeee;
    font-size: 1.0em;
    border-top: 2px solid #333333;
    border-right: 2px solid #333333;
    border-left: 2px solid #333333;
    border-bottom: 2px solid #333333;
}
</style>