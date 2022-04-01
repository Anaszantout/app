<template>
  <!-- Navbar -->
<nav class="navbar navbar-expand-lg navbar-light bg-dark ">
  <!-- Container wrapper -->
  <div class="container  ">
    <!-- Toggle button -->
    <button
      class="navbar-toggler text-light "
      type="button"
      data-mdb-toggle="collapse"
      data-mdb-target="#navbarSupportedContent "
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <i class="fas fa-bars"></i>
    </button>

    <!-- Collapsible wrapper -->
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <!-- Navbar brand -->
      <router-link class="navbar-brand mt-2 mt-lg-0" to="/">
        <i class="fa-brands fa-shopify me-3 text-warning">    E-Shop</i>
      </router-link>
      <!-- Left links -->
      <ul class="navbar-nav me-auto mb-2 mb-lg-0  ">
        <li class="nav-item ">
          <router-link class="nav-link text-light " to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link text-light" to="/about">About Us</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link text-light" to="/products">Products</router-link>
        </li>
      </ul>
      <!-- Left links -->
    </div>
    <!-- Collapsible wrapper -->

    <!-- Right elements -->
    <div class="d-flex align-items-center">
      <!-- Icon -->
      

      <!-- Notifications -->
      <div class="dropdown">
        <a
          class="text-reset me-5 dropdown-toggle hidden-arrow"
          href="#"
          id="navbarDropdownMenuLink"
          role="button"
          data-mdb-toggle="dropdown"
          aria-expanded="false"
        >
         <i class="fas fa-shopping-cart text-light"></i>
          <span v-if="cartItemCount" class="badge rounded-pill badge-notification bg-danger">{{cartItemCount}}</span>
        </a>
        <div
          class="dropdown-menu dropdown-menu-end"
          aria-labelledby="navbarDropdownMenuLink">
          <ShoppingCart />
        </div>
      </div>
      <!-- Avatar -->
      <div class="dropdown" v-if="loggedIn">
        <a
          class="dropdown-toggle d-flex align-items-center  me-4 text-light"
          href="#"
          id="navbarDropdownMenuAvatar"
          role="button"
          data-mdb-toggle="dropdown"
          aria-expanded="false">
         <i class="fa-solid fa-user"></i>
        </a>
        <ul
          class="dropdown-menu dropdown-menu-end"
          aria-labelledby="navbarDropdownMenuAvatar"
        >
          <li>
            <a class="dropdown-item" href="#">My profile</a>
          </li>
          <li>
            <a class="dropdown-item" href="#">Settings</a>
          </li>
          <li>
            <a class="dropdown-item" href="#">Logout</a>
          </li>
        </ul>
      </div>
       <router-link to="/login" class="nav-link text-light" v-else>login</router-link>
    </div>
    <!-- Right elements -->
  </div>
  <!-- Container wrapper -->
</nav>
<!-- Navbar -->
</template>

<script>
import { mapGetters,mapActions } from 'vuex'
import ShoppingCart from './shoppingCart/ShoppingCart.vue'
export default {
  components: { ShoppingCart },
  name: 'PrimaryNavigation',
  computed: {
    ...mapGetters(['cartItemCount','loggedIn'])
  },
  methods: {
    ...mapActions(['logout'])
  }
}
 
</script>

<style scoped>
  .shopping-cart {
    min-width: 450px;
  }
</style>