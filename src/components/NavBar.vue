<template>
  <div id="nav">
    <p class="py-1">Straight to the coffee?<a href="#products" class="mx-1">Shop Now!</a></p>
    <h2><a href="#" id="logo">A&Y Coffee</a></h2> <router-link to="/cart" class="cart-nav"><svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor" class="bi bi-bag" viewBox="0 0 16 16">
  <path d="M8 1a2.5 2.5 0 0 1 2.5 2.5V4h-5v-.5A2.5 2.5 0 0 1 8 1zm3.5 3v-.5a3.5 3.5 0 1 0-7 0V4H1v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V4h-3.5zM2 5h12v9a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V5z"/>
</svg></router-link>
<router-link to="/profile" class="profile-nav"><svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor" class="bi bi-person-fill" viewBox="0 0 16 16">
  <path d="M3 14s-1 0-1-1 1-4 6-4 6 3 6 4-1 1-1 1H3zm5-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6z"/>
</svg></router-link>
    <hr>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About us</router-link>
    <router-link to="/products">Shop</router-link>
    <router-link to="/register">Register</router-link>
    <router-link to="/login">Login</router-link>
    <router-link @click="logout" to="/">Logout</router-link>
    <hr id="hr-b">
  </div>
  <router-view v-slot="{ Component }">
    <transition name="route" mode="out-in">
      <component :is="Component"></component>
    </transition>
  </router-view>
</template>

<script>
export default {
  props: ['isloggedin'],
  methods: {
    logout() {
      localStorage.clear();
    }
  }
}
</script>

<style>
#nav {
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 1000;
    background: #fff;
  }

  #nav #hr-b {
    height: 0.5px;
    margin-bottom: 0;
  }

  #nav #logo {
    font-family: 'Dancing Script', cursive;
    color: #000;
    font-weight: 600;
    text-transform: none;
  }

  #nav p {
    text-transform: uppercase;
    background: #EDE7B1;
    height: 30px;
  }

  #nav a {
    font-weight: bold;
    color: rgb(128, 128, 128);
    text-transform: uppercase;
    transition: 0.3s;
    text-decoration: none;
    margin: 20px;
  }

  #nav a:hover {
    color: #000;
    transition: 00.3s;
  }

  #nav a.router-link-exact-active {
    color: #000;
    transition: 0.3s;
  }

  .cart-nav {
    position: absolute;
    right: 0;
    top: 35px;
    margin-top: auto;
    margin-bottom: auto;
  }

  .profile-nav {
    position: absolute;
    left: 0;
    top: 35px;
    margin-top: auto;
    margin-bottom: auto;
  }

  /* route transition */
  .route-enter-from {
    opacity: 0;
    transform: translateX(100px);
  }

  .route-enter-active {
    transition: all 0.3s ease-out;
  }

  .route-leave-to {
    opacity: 0;
    transform: translateX(-100px);
  }

  .route-leave-active {
    transition: all 0.3s ease-in;
  }

</style>