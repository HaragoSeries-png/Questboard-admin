<template>
  <div>
      <h1>
          Report page
      </h1>
      <div v-for="report in reports" :key="report._id" class="card">
            <div class="by">
                Send by : {{report.sender}}
            </div>
            <div class="detail">
                Detail : {{report.message}}
            </div>
            
      </div>
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
    height: 250;
    border: 1px solid black;
    margin-left: auto;
    margin-right: auto;
}
</style>