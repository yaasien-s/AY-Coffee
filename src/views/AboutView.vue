<template>
  <div class="about-us">
    <p class="py-4 pb-0" style="font-weight: 600;">About us</p>
    <h1>Origin of A&Y Coffee<br>Company</h1>
    <br>
    <br>
    <p class="about-us-desc">We at A&Y Coffee, two life long friends, passionate about coffee and we want everyone else
      to
      enjoy it as much as we do, anytime, anywhere. We want you to enjoy a cup of coffee whether you at work or
      outdoors, coffee is to be enjoyed at anytime of the day. Explore your taste buds trying our vaste range of
      flavourful coffee beans.</p>
    <br><br>

    <div class="container">
      <div class="row">
        <div class="col-sm-3">
          <img src="https://cdn.pixabay.com/photo/2022/01/31/15/18/coffee-6984075_960_720.jpg" alt="coffee-1">
        </div>
        <div class="col-sm-3">
          <img src="https://cdn.pixabay.com/photo/2015/06/24/01/15/coffee-819362_960_720.jpg" alt="coffee-2">
        </div>
        <div class="col-sm-3">
          <img src="https://cdn.pixabay.com/photo/2017/06/20/22/14/man-2425121_960_720.jpg" alt="coffee-3">
        </div>
        <div class="col-sm-3">
          <img src="https://cdn.pixabay.com/photo/2021/12/18/07/55/cup-6878196_960_720.jpg" alt="coffee-4">
        </div>
      </div>
    </div>

    <h1 class="mb-5">Our Vision</h1>
    <p class="about-us-desc">At A&Y's Coffee Company we want to improve the lives of our guests, support the communities
      we serve to promote our common humanity. A&Y Coffee to be the leading coffee store and purveyor of gourmet
      coffees, and food service products around the world by offering the guiding principles of integrity, quality,
      service and relationship.</p>
  </div>
 
</template>

<script>
  export default {

  }
</script>

<style>
  .about-us {
    margin-top: 150px;
  }

  .about-us h1 {
    font-weight: 600;
  }

  .about-us-desc {
    width: 800px;
    margin-left: auto;
    margin-right: auto;
    font-weight: 600;
  }

  .container {
    margin-bottom: 50px;
  }

  .col-sm-3 {
    padding: 0 !important;
  }

  .col-sm-3 img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

 
  @media (max-width: 770px) {
    .about-us-desc {
      width: 100%;
    }

    .col-sm-3 img {
      width: 100%;
      height: 100%;
    }
  }
</style>