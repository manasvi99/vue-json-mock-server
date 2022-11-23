<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <FetchData/>
  <table>
    <tr>
      <td>firstname</td>
      <td>lastname</td>
    </tr>
    <tr>
      <td>{{employee.fname}}</td>
      <td>{{employee.lname}}</td>
    </tr>
  </table>
</template>

<script>
import FetchData from './components/FetchData.vue'

import axios from 'axios'
//import emplyeejson from './employee.json'
export default {
  name: 'App',
  components: {
    FetchData
  },
  data(){
    return{
      employee:{}
    }
  },
   mounted() {
    axios.get('http://localhost:3002/api/employee').then((response)=>{
      //console.log(response.data);
      this.employee=response.data;
    }
    ).catch((error)=>{
      console.log("error" +error);
    }).finally(()=>{
      console.log("always execute");
    });
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
