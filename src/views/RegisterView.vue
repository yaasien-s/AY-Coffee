<template>
  <div class="register" @submit.prevent="register">
    <h1 class="my-4">Create An Account</h1>

    <form action="">
      <label for="">Full Name <span>*</span></label>
      <input type="name" required v-model="fullname">

      <label for="">Email <span>*</span></label>
      <input type="email" required v-model="email">

      <label for="">Contact Number <span>*</span></label>
      <input type="contact" required v-model="contact">

      <label for="">Password <span>*</span></label>
      <input type="password" required v-model="password">

      <button type="submit" class="my-4">Sign Up</button>

      <p style="font-weight: 600;">Already a member? <a href="#login">Sign in</a></p>
    </form>

  </div>
</template>

<script>
export default {
  data() {
    return {
      fullname: "",
      email: "",
      contact: "",
      password: "",
    };
  },
  methods: {
    register() {
      fetch("https://collab-backend-pos.herokuapp.com/users", {
        method: "POST",
        body: JSON.stringify({
          fullname: this.fullname,
          email: this.email,
          contact: this.contact,
          password: this.password,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          this.msg = `${ this.name } registered Successfully`;
          alert("redirecting to Login...");
          localStorage.setItem("jwt", json.jwt);
          this.$router.push({ name: "Products" });
        })
        .catch((err) => {
          alert(err);
        });
    },
  },
};
</script>

<style scoped>
.register {
  margin-top: 150px;
  padding-top: 20px;
}

form {
  display: grid;
  width: 35%;
  margin-left: auto;
  margin-right: auto;
  background: #fff;
  padding: 50px;
}

form label {
  text-align: initial;
  margin: 10px;
  font-weight: 600;
  margin-left: 0;
}

form button {
  border: none;
  background: #9A6D38;
  height: 40px;
  transition: 00.3s;
  font-weight: 600;
}

form button:hover {
  background: #EDE7B1;
  transition: 00.3s;
}

form span {
  color: red;
}

@media (max-width: 1000px) {
  form {
    width: fit-content;
  }
}
</style>
