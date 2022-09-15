<template>
    <h1>App fruits</h1>
<SelectFruits v-bind:list="list" />
</template>

<script>



import SelectFruits from './components/SelectFruits.vue'

    export default {
      name:"App",
      components: {
        SelectFruits
      },

      data() {
        return { 
          list:[]
         } 
      },

      
 async mounted() {
    const api = "http://127.0.0.1:8888/api/fruits"
     const response = await fetch(api)
     const data = await response.json()
    // console.log(data.data);
    this.list=data.data.fruits
      }
  }

</script>

<style>
    body {
      background:#ccc;
    }
</style>