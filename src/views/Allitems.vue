<template>
  <div class="testing container">
    <h1>This is an all items page</h1>
    <div class="row mt-3">
      <p v-if="error">Server Error!</p>
      <Item v-for="(item,index) in items" :key="index" :item="item" v-else></Item>
    </div>
  </div>
</template>

<script type="text/javascript">
  import Service from '@/services/Service.js'
  import Item from '@/components/Item.vue'

  export default{
    name: 'Testing',
    components:{
      Item
    },
    data(){
      return {
        error: false,
        items:[]
      }
    },
    created(){
      Service.getItems()
        .then(response => {
          // console.log(response.data.items)
          this.items = response.data.items
        })
        .catch(error => {
          this.error = true
          console.log('There was an error:',error.response)
        })
    },
    methods:{
      
    },
    computed:{
      
    }
  }
</script>

<style type="text/css">
  
</style>