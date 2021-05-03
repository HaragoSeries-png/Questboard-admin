<template>
  <div>
      <h1>
          Report page
      </h1>
  <v-row style="padding-left:5%;">
  <v-card style="width:300px;margin-top:5%;margin-left:5%;" v-for="report in reports" :key="report._id" >
    <v-card-text>
          Send by   {{report.sender}}
    </v-card-text>
      <v-card-actions>
        <v-list-item  >
          <v-list-item-content style="height:150px;overflow-y:scroll;" >
            <v-card-textarea >Detail: {{report.message}} </v-card-textarea>
          </v-list-item-content>
        </v-list-item>
      </v-card-actions>
  </v-card>
  
  </v-row>
  
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
</style>