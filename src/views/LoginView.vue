<template>
  <div class="login">
    <h1 class="my-4">Login</h1>

    <form @submit.prevent="login" id="login-form">
      <label for="">Email</label>
      <input type="email" name="" id="" v-model="email" required>

      <label for="">Password</label>
      <input type="password" name="" id="" v-model="password" required>

      <button type="submit" class="my-4" @click="login">Sign in</button>

      <p style="font-weight: 600;">Not a member? <a href="#register">Create an account</a></p>
    </form>

  </div>
</template>

<script>
  export default {
    data() {
      return {
        email: "",
        password: "",
      };
    },
    methods: {
      login() {
        fetch('https://collab-backend-pos.herokuapp.com/users', {
            method: 'PATCH',
            body: JSON.stringify({
              email: this.email,
              password: this.password,
            }),
            headers: {
              'Content-type': 'application/json; charset=UTF-8',
            },
          })
          .then((response) => response.json())
          .then((json) => {
            localStorage.setItem("jwt", json.jwt);
            alert("User logged in");
            this.$router.push({
              name: "Products"
            });
          })
          .catch((err) => {
            alert(err);
          });
      },
    },
  };
</script>

<style scoped>
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