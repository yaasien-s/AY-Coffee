<template>
  <div id="nav">
    <p class="py-1">Straight to the coffee?<a href="#products" class="mx-1">Shop Now!</a></p>
    <h2><a href="#" id="logo">A&Y Coffee</a></h2> <router-link to="/cart" class="cart-nav"><svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor" class="bi bi-bag" viewBox="0 0 16 16">
  <path d="M8 1a2.5 2.5 0 0 1 2.5 2.5V4h-5v-.5A2.5 2.5 0 0 1 8 1zm3.5 3v-.5a3.5 3.5 0 1 0-7 0V4H1v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V4h-3.5zM2 5h12v9a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V5z"/>
</svg></router-link>
    <hr>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About us</router-link>
    <router-link to="/products">Shop</router-link>
    <router-link to="/register">Register</router-link>
    <router-link to="/login">Login</router-link>
    <hr id="hr-b">
  </div>
  <router-view v-slot="{ Component }">
    <transition name="route" mode="out-in">
      <component :is="Component"></component>
    </transition>
  </router-view>

   <br><br>
    <div class="scroll-to-top">
    <button @click="scrollToTop">Scroll to top</button>
  </div>
  <footer>
    <br>
    <p>A&Y Coffee Co.
      <br><br>
      We believe that the coffee experience should be enjoyed anywhere and anytime. Our mission is to bring you closer
      to the enjoyment of coffee whether at home, work or outdoors. Enjoy the journey of brewing your own cup and fill
      your soul with the delicious aroma of freshly ground beans.</p>
    <hr>
    <p id="f-text">Copyright 2022 © A&Y Coffee Co.</p>
  </footer>
</template>
<script>
export default {
  name: "App",
  methods: {
    scrollToTop() {
      let currentScroll = document.documentElement.scrollTop,
      int = setInterval(frame, 6)

      function frame() {
        if(0 > currentScroll)
        clearInterval(int)
        else {
          currentScroll = currentScroll - 12
          document.documentElement.scrollTop = currentScroll
        }
      }
    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap');

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

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

  footer {
    background: #9A6D38;
    height: auto;
    color: #fff;
  }

  footer p {
    width: 75%;
    text-align: center;
    margin: auto;
  }

  #f-text {
    margin-bottom: 0;
    padding-bottom: 10px;
    margin-right: auto;
    margin-left: auto;
  }

  footer hr {
    height: 3px !important;
    font-size: 10px;
    width: 75%;
    margin-right: auto;
    margin-left: auto;
  }

  .scroll-to-top {
    padding: 30px 0;
    position: fixed;
    right: 10px;
    bottom: 0;
  }

  .scroll-to-top button {
    border: none;
    background: #9A6D38;
    color: #fff;
    cursor: pointer;
  }
</style>