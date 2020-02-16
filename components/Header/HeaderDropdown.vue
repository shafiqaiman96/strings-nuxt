<template>
      <b-nav-item-dropdown right no-caret style="padding-left: 140px">
        <template slot="button-content">
          <img src="~static/img/avatars/3.jpg" class="img-avatar" alt="admin@bootstrapmaster.com">
        </template>
        <b-dropdown-header class="text-center"><strong>Account</strong></b-dropdown-header>
        <!-- <b-dropdown-item><i class="fa fa-bell-o"></i> Updates<b-badge variant="info">{{itemsCount}}</b-badge></b-dropdown-item>
        <b-dropdown-item><i class="fa fa-envelope-o"></i> Messages<b-badge variant="success">{{itemsCount}}</b-badge></b-dropdown-item>
        <b-dropdown-item><i class="fa fa-tasks"></i> Tasks<b-badge variant="danger">{{itemsCount}}</b-badge></b-dropdown-item>
        <b-dropdown-item><i class="fa fa-comments"></i> Comments<b-badge variant="warning">{{itemsCount}}</b-badge></b-dropdown-item>
        <b-dropdown-header class="text-center"><strong>Settings</strong></b-dropdown-header> -->
        <b-dropdown-item><i class="fa fa-user"></i><nuxt-link to="/base/profile"> Profile</nuxt-link></b-dropdown-item>
        <b-dropdown-item><i class="fa fa-wrench"></i><nuxt-link to="/base/profile">Settings</nuxt-link></b-dropdown-item>
        <!-- <b-dropdown-item><i class="fa fa-usd"></i> Payments<b-badge variant="secondary">{{itemsCount}}</b-badge></b-dropdown-item>
        <b-dropdown-item><i class="fa fa-file"></i> Projects<b-badge variant="primary">{{itemsCount}}</b-badge></b-dropdown-item> -->
        <b-dropdown-divider></b-dropdown-divider>
        <!-- <b-dropdown-item><i class="fa fa-shield"></i> Lock Account</b-dropdown-item> -->
        <b-dropdown-item @click="logout"><i class="fa fa-lock"></i><nuxt-link to="/pages/login"> Logout</nuxt-link></b-dropdown-item>
      </b-nav-item-dropdown>
</template>

<script>
  export default {
    name: 'header-dropdown',
    data: () => {
      return { itemsCount: 42 }
    },
    methods: {
      async logout() {
        try {
          this.$store.dispatch('logout').then(() => {
            this.$router.push('/login')
          })
        } catch (e) {
          this.formError = e.message
        }
      }
    }
  }
</script>

