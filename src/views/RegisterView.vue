<template>
  <div class="register">
    <h1 class="my-4">Create An Account</h1>

    <form action="">
      <label for="">Full Name <span>*</span></label>
      <input type="text" required>

      <label for="">Email <span>*</span></label>
      <input type="text" required>

      <label for="">Contact Number <span>*</span></label>
      <input type="text" required>

      <label for="">Password <span>*</span></label>
      <input type="text" required>

      <button type="submit" class="my-4">Sign Up</button>

      <p style="font-weight: 600;">Already a member? <a href="#login">Sign in</a></p>
    </form>

  </div>
</template>

<style>
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

input {
  opacity: 0.5;
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
