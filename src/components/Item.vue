<template>
  <div class="col-md-4">
    <div class="card">
      <img v-bind:src="item.image" class="card-img-top">
      <div class="card-body">
        <p class="card-text">{{item.name}} - {{item.price}} Ks</p>
        <router-link :to="{name: 'itemdetail', params: { id: item.id }}">
          <b-button variant="primary">Show Detail <b-icon icon="arrow-return-right"></b-icon></b-button>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  export default{
    name: 'Item',
    props: {
      item: Object
    },
    data(){
      return {

      }
    }
  }
</script>

<style type="text/css">
  
</style>