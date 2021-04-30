<template>
   <div>
  <p v-for="item in all" :key="item.id"  >
    {{item.id}} - {{item.title}} - <b v-bind:class="item.completed==false?'red':'green'">{{item.completed}}</b>
  </p>
   </div>
</template>

<script>
import axios from 'axios';

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
      axios.get('https://jsonplaceholder.typicode.com/todos').then(
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