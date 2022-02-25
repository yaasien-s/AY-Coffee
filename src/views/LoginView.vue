<template>
  <div class="login">
      <h1 class="my-4">Login</h1>
      
      <form action="" id="login-form">
        <label for="">Email</label>
        <input type="text" name="" id="">

        <label for="">Password</label>
        <input type="text" name="" id="">

        <button class="my-4">Sign in</button>

        <p style="font-weight: 600;">Not a member? <a href="#register">Create an account</a></p>
      </form>

  </div>
</template>

<script>
export default {

}
</script>

<style>
.login {
    margin-top: 150px;
    padding-top: 20px;
}

#login-form {
  display: grid;
  width: 35%;
  margin-left: auto;
  margin-right: auto;
  background: #fff;
  padding: 50px;
}

#login-form label {
  text-align: initial;
  margin: 10px;
  font-weight: 600;
  margin-left: 0;
}

#login-form button {
  border: none;
  background: #9A6D38;
  height: 40px;
  transition: 00.3s;
  font-weight: 600;
}

input {
  opacity: 0.5;
}

#login-form button:hover {
  background: #EDE7B1;
  transition: 00.3s;
}

@media (max-width: 1000px) {
  #login-form {
    width: fit-content;
  }
}
</style>