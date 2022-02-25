<template>
  <div class="home">
    <h1>Welcome to A&Y <br> Coffee Company new online store</h1>
    <a href="#products">
      <button>Shop Now</button>
    </a>
  </div>
  <h3 class="mt-5" style="font-weight: 600;">@A&YCoffee.Co</h3>
  <p class="my-3" style="font-weight: 600;">Follow us on Instagram</p>
  <br>
  <div class="container insta">
    <div class="row">
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2017/03/27/14/18/coffee-2179028__340.jpg" alt="">
      </div>
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2019/11/11/15/32/coffee-4618705__340.jpg" alt="">
      </div>
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2017/05/16/21/45/coffee-2319107__340.jpg" alt="">
      </div>
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2016/11/19/12/54/cake-1839134__340.jpg" alt="">
      </div>
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2019/07/13/11/44/coffee-4334647__340.jpg" alt="">
      </div>
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2021/09/06/01/13/coffee-6600644__340.jpg" alt="">
      </div>
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2021/12/18/07/55/cup-6878196__340.jpg" alt="">
      </div>
      <div class="col-sm-3 my-1">
        <img src="https://cdn.pixabay.com/photo/2018/01/31/09/57/coffee-3120750__340.jpg" alt="">
      </div>
    </div>
  </div>
</template>

<script>
  // @ is an alias to /src
  // import Footer from '@/components/Footer.vue'

  export default {}
</script>

<style>
  .home {
    margin-top: 150px;
    background: url(https://wallpaper.dog/large/20496014.jpg);
    width: 100%;
    height: 78.5vh;
    object-fit: cover;
    background-repeat: no-repeat;
    background-size: cover;
  }

  .home h1 {
    font-weight: 600;
    color: #000;
    margin-top: auto;
    margin-bottom: auto;
    margin-left: 70px;
    left: 0;
    text-align: initial;
    padding-top: 200px;
  }

  .home button {
    margin-top: 20px;
    position: absolute;
    left: 70px;
    background: #EDE7B1;
    border: none;
    height: 50px;
    width: 125px;
    font-weight: 600;
    font-size: 1.1rem;
    transition: 00.3s;
    text-transform: uppercase;
  }
  .home button:hover {
    background: #000;
    color: #EDE7B1;
    transition: 00.3s;
  }

</style>