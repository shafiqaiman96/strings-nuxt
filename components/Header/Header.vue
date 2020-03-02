<template>
  <!-- <header class="app-header navbar">
    <button class="navbar-toggler mobile-sidebar-toggler d-lg-none" type="button" @click="mobileSidebarToggle">
      <span class="navbar-toggler-icon"></span>
    </button>
    <b-link class="navbar-brand" to="#"></b-link>
    <button class="navbar-toggler sidebar-toggler d-md-down-none" type="button" @click="sidebarToggle">
      <span class="navbar-toggler-icon"></span>
      
    </button> -->
    
    <!-- <b-navbar-nav class="d-md-down-none">
      <b-nav-item class="px-3">Dashboard</b-nav-item>
      <b-nav-item class="px-3">Users</b-nav-item>
      <b-nav-item class="px-3">Settings</b-nav-item>
    </b-navbar-nav> -->
    <!-- <b-navbar-nav class="ml-auto"> -->
      <!-- <b-nav-item class="d-md-down-none">
        <i class="icon-bell"></i>
        <b-badge pill variant="danger">5</b-badge>
      </b-nav-item>
      <b-nav-item class="d-md-down-none">
        <i class="icon-list"></i>
      </b-nav-item>
      <b-nav-item class="d-md-down-none">
        <i class="icon-location-pin"></i>
      </b-nav-item> -->
      <!-- <HeaderDropdown/> -->
    <!-- </b-navbar-nav> -->
    <!-- <button class="navbar-toggler aside-menu-toggler d-md-down-none" type="button" @click="asideToggle">
      <span class="navbar-toggler-icon"></span>
    </button> -->
    <div>
  <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#"><img src="https://strings.my/wp-content/uploads/2019/10/strings-9.png" style="width:120px"></b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav style="height: 30px">
<div id="mainNav">

 <!-- The navigation menu will get the value of the "active" variable as a class. -->

 <!-- To stops the page from jumping when a link is clicked 
        we use the "prevent" modifier (short for preventDefault). -->
<a style="float-left; padding-left:50px;" href="/"><i class="fa fa-home fa-3x" aria-hidden="true"></i> </a>
 <nav v-bind:class="activeClass" v-for="routes in itemNav" v-bind:key="routes.id">
  <a :class="{ 'active': index === 0 }"><nuxt-link :to="`${routes.url}`">{{routes.name}}</nuxt-link></a>
  <!-- <a href="#" class="projects" v-on:click="makeActive('projects')"><nuxt-link to="/base/profile">Projects</nuxt-link></a>
  <a href="#" class="services" v-on:click="makeActive('services')"><nuxt-link to="/base/forms">Services</nuxt-link></a>
  <a href="#" class="contact" v-on:click="makeActive('contact')"><nuxt-link to="/base/paginations">Contact</nuxt-link></a> -->
 </nav>
</div>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
          <HeaderDropdown/>
        <!-- <b-nav-item-dropdown right> -->
          <!-- Using 'button-content' slot -->
          <!-- <template v-slot:button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown> -->
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
  <!-- </header> -->
</template>

<script>
  import HeaderDropdown from './HeaderDropdown.vue'
  export default {
    name: 'c-header',
    components: {
      HeaderDropdown
    },
    methods: {
      sidebarToggle (e) {
        e.preventDefault()
        document.body.classList.toggle('sidebar-hidden')
      },
      sidebarMinimize (e) {
        e.preventDefault()
        document.body.classList.toggle('sidebar-minimized')
      },
      mobileSidebarToggle (e) {
        e.preventDefault()
        document.body.classList.toggle('sidebar-mobile-show')
      },
      asideToggle (e) {
        e.preventDefault()
        document.body.classList.toggle('aside-menu-hidden')
      }
    },

    // This is the model.
	// Define properties and give them initial values.
  data: function() {
  return {
    itemNav: [
      // {
      //   name: 'Home',
      //   url: '/',
      // },
      {
        name: 'Account & Banking',
        url: '/base/account',
      },
      {
        name: 'Investment and Loans',
        url: '/pages/maintenance',
      },
      {
        name: 'Insurance',
        url: '/pages/maintenance',
      },
      {
        name: 'Payment',
        url: '/base/payment',
      },
      {
        name: 'Top Up',
        url: '/base/topup',
      },
      {
        name: 'Transfer',
        url: '/base/transfer',
      }
    ]
  };
},
}
</script>

<style scoped>
.active {
  color: azure;
  text-align: center;
  padding-top: 25px;
  background-color: rgb(38, 144, 177);
  border: 0.5px solid rgb(29, 98, 119);
  height: 60px;
  border-radius: 5px
}
a, a:visited {
	outline:none;
	color:#ffffff;
}

</style>

<style>

a:hover{
	text-decoration:none;
}

section, footer, header, aside, nav{
	display: block;
}

/*-------------------------
	The menu
--------------------------*/

nav{
	display:inline-block;
	/* margin:10px; */
	/* background-color:#5597b4; */
	/* box-shadow:0 1px 1px #ccc; */
	border-radius:2px;
}

nav a{
	display:inline-block;
	padding: 10px;
	font-weight:bold;
	font-size:12px;
	text-decoration:none !important;
	line-height:1;
	text-transform: uppercase;
	background-color:transparent;

	-webkit-transition:background-color 0.25s;
	-moz-transition:background-color 0.25s;
	transition:background-color 0.25s;
}

nav a:first-child{
	border-radius:2px 0 0 2px;
}

nav a:last-child{
	border-radius:0 2px 2px 0;
}

nav.home .home,
nav.projects .projects,
nav.services .services,
nav.contact .contact{
	background-color: #ff3a3acf;
}

/* p{
	font-size:22px;
	font-weight:bold;
	color:#7d9098;
} */

/* p b{
	color:#ffffff;
	display:inline-block;
	padding:5px 10px;
	background-color:#c4d7e0;
	border-radius:2px;
	text-transform:uppercase;
	font-size:18px;
} */
</style>