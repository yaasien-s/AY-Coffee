<template>
<NavBar/>
   <br><br>
    <div class="scroll-to-top">
    <button @click="scrollToTop">Scroll to top</button>
  </div>
  <Footer/>
</template>
<script>
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
export default {
  components: {
    NavBar,
    Footer
  },
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