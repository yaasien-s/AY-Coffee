<template>
    <div class="cart">
        <h1>Cart</h1>
        <h3 style="font-weight: 600;"><a href="#cart">SHOPPING CART</a> <span style="color: grey;"> > </span>
            <a href="#">CHECKOUT DETAILS</a> <span style="color: grey;"> > </span>
            ORDER COMPLETE</h3>
        <button style="text-transform: uppercase;"><a href="#products">Return to shop</a></button>
    </div>
</template>

<script>
    export default {

    }
</script>

<style>
    .cart {
        margin-top: 150px;
        padding-top: 20px;
    }

    .cart h3 a {
        color: rgb(128, 128, 128);
        text-decoration: none;
        font-weight: 600;
    }

    .cart h3 a:hover {
        color: #000;
    }

    .cart button {
        border: none;
        background: #9A6D38;
        height: 40px;
        transition: 00.3s;
        font-weight: 600;
    }

    .cart button a {
        text-decoration: none;
        color: #000;
    }

    .cart button:hover {
        background: #EDE7B1;
        transition: 00.3s;
    }
</style>