<template>
    <div class="profile">
        <h1>Profile Page</h1>
        <div class="container">
            <div class="row">
                <div class="mt-5">
                    <h3>User Information</h3>
                    <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor"
                        class="bi bi-person-circle" viewBox="0 0 16 16">
                        <path d="M11 6a3 3 0 1 1-6 0 3 3 0 0 1 6 0z" />
                        <path fill-rule="evenodd"
                            d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8zm8-7a7 7 0 0 0-5.468 11.37C3.242 11.226 4.805 10 8 10s4.757 1.225 5.468 2.37A7 7 0 0 0 8 1z" />
                    </svg>
                    <div id="user-info" v-for="user in users" :key="user._id">
                    <p class="mt-4">Full Name : {{user.fullname}} </p>
                    <p class="my-4">Email : {{user.email}} </p>
                    <p class="mb-4">Contact No. : {{user.contact}} </p>
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
        users: null,
        name: "",
        email: "",
        contact: ""

      };
    },
    // fetching user infpo
    created() {
      if (localStorage.getUser("jwt")) {
        fetch("https://collab-backend-pos.herokuapp.com/users", {
            method: "GET",
            headers: {
              "Content-type": "application/json; charset=UTF-8",
              Authorization: `Bearer ${localStorage.getUser("jwt")}`,
            },
          })
          .then((response) => response.json())
          .then((json) => {
            this.users = json;
            this.users.forEach(async (user) => {
              await fetch(
                  "https://collab-backend-pos.herokuapp.com/users" + user._id, {
                    method: "GET",
                    headers: {
                      "Content-type": "application/json; charset=UTF-8",
                      Authorization: `Bearer ${localStorage.getUser("jwt")}`,
                    },
                  }
                )
                .then((response) => response.json())
                .then((json) => {
                  user.author = json.name;
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
    }
</script>

<style>
    .profile {
        margin-top: 150px;
        padding-top: 20px;
    }

    #user-info {
        width: 40%;
        margin-top: 20px;
        margin-right: auto;
        margin-left: auto;
        text-align: initial;
        border: 1px solid #000;
        border-radius: 5px;
        padding: 20px;
        font-weight: 600;
    }
</style>