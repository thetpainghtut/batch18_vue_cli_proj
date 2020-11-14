<template>
  <div class="testing container">
    <h1>This is an item detail page</h1>
    <div class="row mt-3">
      <p v-if="error">Server Error!</p>
      <div class="col-md-12" v-else>
        <div class="card mb-3">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img :src="item.image" class="card-img" alt="...">
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <h5 class="card-title">{{item.name}} - {{item.price}} Ks</h5>
                <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
                <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  import Service from '@/services/Service.js'

  export default{
    name: 'Itemdetail',
    data(){
      return {
        error: false,
        item:Object
      }
    },
    created(){
      let id = this.$route.params.id;

      Service.getItem(id)
        .then(response => {
          // console.log(response.data.items)
          this.item = response.data.item
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