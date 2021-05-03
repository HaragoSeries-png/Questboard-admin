<template>
  <div>
      <h1>
          Report page
      </h1>
      
           <v-card v-for="report in reports" :key="report._id" class="card"
      color="#26c6da"
      dark
      max-width="600"
    > 
      <v-card-text class="font-weight-bold">
       {{report.sender}}
      </v-card-text>
      <v-card-actions>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>{{report.message}}</v-list-item-title>
          </v-list-item-content>
          <v-row
            align="center"
            justify="end"
          >
          </v-row>
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
    width: 300px;
    height:250px;
    border: 1px solid black;
}
</style>