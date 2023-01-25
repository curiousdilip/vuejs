<template>
  <div class="loginContainer">
    <img src="../assets/logo.svg" alt="Logo" class="logo" />
    <h1>Login</h1>
    <div class="login">
      <input type="text" v-model="email" placeholder="Enter Email" />
      <input type="password" v-model="password" placeholder="Enter Password" />
      <button v-on:click="login">Login</button>
      <p>
        <router-link to="/sign-up">Sign Up</router-link>
      </p>
    </div>
  </div>
</template>


<script>
import axios from "axios";
export default {
  /* eslint-disable */ name: "Login",
  date() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    async login() {
      let result = await axios.get(
        `http://localhost:3000/users?email=${this.email}&password=${this.password}`
      );
      if (result.status == 200 && result.data.length > 0) {
        localStorage.setItem("user-info", JSON.stringify(result.data[0]));
        this.$router.push({ name: "Home" });
      }
    },
  },
  mounted() {
    let user = localStorage.getItem("user-info");
    if (user) {
      this.$router.push({ name: "Home" });
    }
  },
};
</script>
<style>
.loginContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 95vh;
}

.logo {
  width: 100px;
}

.login input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 20px;
  border: 1px solid gray;
  border-radius: 30px;
}

.login button {
  width: 100px;
  height: 40px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 20px;
  background-color: orange;
  border: 1px solid gray;
  border-radius: 30px;
}

.login button:hover {
  background-color: white;
  color: orange;
  border: 1px solid orange;
}

p {
  text-align: center;
}
</style>