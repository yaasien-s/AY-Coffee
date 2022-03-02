<template>
  <div class="products">
    <div style="text-align:center">

      <h1 style="text-align:center">Products</h1>
      <!-- Button trigger modal -->
      <button type="button" class="btn my-5" id="product-btn" data-bs-toggle="modal" data-bs-target="#exampleModal">
        Add a product
      </button>
    </div>

    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Add Product</h5>

            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            ...
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>


    <div class="container">
      <div class="row">


        <div v-for="product of products" :key="product.name" class="card mx-5 my-5 col-sm-3 p-0">
          <img :src="product.img" class="card-img-top" alt="...">
          <div class="card-body">
            <!-- <h5 class="card-title" style="font-weight: 600;">{{product.title}}</h5> -->
            <h6 style="font-weight: 600;">{{product.description}}</h6>
            <p class="card-text text-secondary">{{product.category}}</p>
            <p class="card-text text-dark" style="font-weight: 600;">R {{product.price}}</p>
            <a href="#" class="btn" id="product-btn">Add to cart</a>
          </div>
        </div>

      </div>
    </div>



  </div>


</template>

<script>
  export default {
    data() {
      return {
        products: null,
      };
    },
    // fetching product
    created() {
      if (localStorage.getItem("jwt")) {
        fetch("https://collab-backend-pos.herokuapp.com/products", {
            method: "GET",
            headers: {
              "Content-type": "application/json; charset=UTF-8",
              Authorization: `Bearer ${localStorage.getItem("jwt")}`,
            },
          })
          .then((response) => response.json())
          .then((json) => {
            this.products = json;
            this.products.forEach(async (product) => {
              await fetch(
                  "https://collab-backend-pos.herokuapp.com/products" + product.name, {
                    method: "GET",
                    headers: {
                      "Content-type": "application/json; charset=UTF-8",
                      Authorization: `Bearer ${localStorage.getItem("jwt")}`,
                    },
                  }
                )
                .then((response) => response.json())
                .then((json) => {
                  product.author = json.name;
                });
            });
          })
          .catch((err) => {
            alert("Log in failed");
          });
      } else {
        alert("Not logged in");
        this.$router.push({
          name: "Login"
        });
      }

    },
  };
</script>

<style scoped>
  .products {
    margin-top: 150px;
    padding-top: 20px;
  }

  .card {
    margin-right: auto !important;
    margin-left: auto !important;
    border-bottom-left-radius: 20px;
    border-bottom-right-radius: 20px;
    background: transparent;
    border: none;
  }

  .card-body {
    /* border-top: 2px solid black; */
    margin-top: 5px;
    background: transparent;
    text-align: initial;
    margin-left: 10px;
  }

  .card-body .text-secondary {
    color: #9A6D38 !important;
    font-weight: 600;
  }

  .card-img-top {
    width: 85%;
    height: 85%;
    object-fit: cover;
    margin-inline: auto;

  }

  #product-btn {
    background-color: #9A6D38;
    font-weight: 600;
  }

  #product-btn:hover {
    background-color: #000;
    color: #9A6D38;
    font-weight: 600;
  }
</style>