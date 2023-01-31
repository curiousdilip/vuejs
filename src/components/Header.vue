<template>
  <div class="nav">
    <router-link to="/">Home</router-link>
    <router-link to="/add-restaurant">Add Restaurant</router-link>
    <router-link to="#" v-on:click="logout">Logout</router-link>
  </div>
</template>

<script>
export default {
  /* eslint-disable */ name: "Header",
  methods: {
    logout() {
      localStorage.clear();
      this.$router.push({ name: "Login" });
    },
  },
};
</script>

<style>
.nav {
  background-color: #333;
  /* height: 100px; */
  overflow: hidden;
}

.nav a {
  float: left;
  color: #f2f2f2;
  padding: 14px 16px;
  text-align: center;
  text-decoration: none;
  font-size: 17px;
  margin-left: 5px;
}

.nav a:hover {
  background: #ddd;
  color: #333;
}
</style>