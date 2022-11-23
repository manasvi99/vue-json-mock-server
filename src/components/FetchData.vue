<template>
   <h2>
       
   <tr>
       <td>firstname</td>
   </tr>
   <tr  v-for="employee in employees" :key="employee.fname">
       {{employee.fname}}
   </tr>
   </h2>
</template>

<script>
import axios from 'axios'
export default {
 data(){
     return{
         employees:[]
     }
 },
 mounted(){
     axios.get('http://localhost:3002/api/employees').then((response)=>{
        this.employees=response.data.emplyees;      
     }).catch((error)=>{
         console.log("error"+error);
     }).finally(()=>{
         console.log("always executes");
     })
 }
}
</script>

<style>

</style>