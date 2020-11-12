<template>
  <div class="testing container">
    <h1>This is an testing page</h1>
    <p class="text-danger">{{name}}</p>

    <div class="row">
      <div class="col-md-4" v-for="(item,index) in items" :key="index">
        <div class="card">
          <img v-bind:src="item.image" class="card-img-top">
          <div class="card-body">
            <p class="card-text">{{item.name}} - {{item.price}} Ks</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  import Service from '@/services/Service.js'

  export default{
    data(){
      return {
        name:'Mg Mg',
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
          console.log('There was an error:',error.response)
        })
    },
    methods:{

    }
  }
</script>

<style type="text/css">
  
</style>