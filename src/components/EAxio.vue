<template>
   <div>
     <table border="2">
       <thead>
          <td>
            <tr>ID</tr>
          </td>
          <td>
            <tr>TITLE</tr>
          </td>
          <td>
            <tr>STATUS</tr>
          </td>
       </thead>
       <tbody v-for="item in all" :key="item.id" >
           <td>
             <tr>{{item.id}}</tr>
           </td>
           <td>
             <tr>{{item.title}}</tr>
           </td>
           <td>
             <tr v-bind:class="item.completed==false?'red':'green'">{{item.completed}}</tr>
           </td>
       </tbody>
     </table>
   </div>
</template>

<script>
//import axios from 'axios';

export default {
name: 'EAxio',
  data(){
  return{
    all: ''
  }
  },
  mounted() {
  console.log('start...')
  this.getData();
  },
  methods: {
    getData(){
      console.log('enter to the method')
      this.axios.get("https://jsonplaceholder.typicode.com/todos").then(
          response => {
            console.log(response)
            this.all = response.data
          }
      ).catch(
          e => console.log(e)
      )
    }
  },
}

</script>

<style scoped>
.red{
  color: red;
}
.green{
  color: green;
}



</style>