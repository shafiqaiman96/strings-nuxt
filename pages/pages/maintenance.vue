<template>
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="6">
          <div class="clearfix">            
            <img src="https://5.imimg.com/data5/MJ/QE/MV/SELLER-21032740/work-under-maintenance-sign-board-500x500.jpg">
            <h4 class="pt-3">This page is under maintenance <button style="float: right"  v-bind:class="activeClass" v-for="routes in back" v-bind:key="routes.id"><nuxt-link :to="`${routes.url}`">Back</nuxt-link></button></h4>
          </div>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Maintenance',
  layout: 'clean',
  data: function() {
  return {
    back: [
      {
        name: 'Home',
        url: '/',
      },
    ]
  };
  }
}
</script>
