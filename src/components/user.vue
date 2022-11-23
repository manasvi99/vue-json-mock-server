<template>
 <table  :style="background">
     <tr>
         <td>id</td>
         <td>email</td>
        <td>first_name</td>
        <td>last_name</td>
        <td>avatar</td>
     </tr>
     <tr v-for="user in users" :key="user.id">
      <td>
         {{user.id}}
      </td>
      <td>  {{user.email}}
      </td>
      <td> 
          {{user.first_name}}
    </td>
      <td>  
          {{user.last_name}}
          </td>
      <td>  
          <img :src="user.avatar" alt="" srcset="">
          
          </td>
     </tr>
     <tr>
         <td>
             <button @click="fetchapi">submit</button>
         </td>
     </tr>
 </table>
</template>

<script>
import axios from 'axios'
export default {

data(){
    return{
        users:[],
        background:"background-color:red"
    }
},
/*mounted(){
    axios.get('https://reqres.in/api/users').then((response)=>{
        this.users=response.data.data;
        console.log(response.data.data);

    }).catch((error)=>{
        console.log("error"+error);
    }).finally(()=>{
        console.log("never fail to execute");
    })
},*/
methods:{
   fetchapi(){
       axios.get('https://reqres.in/api/users').then((response)=>{
        this.users=response.data.data;
        console.log(response.data.data);

    }).catch((error)=>{
        console.log("error"+error);
    }).finally(()=>{
        console.log("never fail to execute");
    })
   }
}
}
</script>

<style>

</style>