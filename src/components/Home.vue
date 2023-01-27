<template>
  <Header />
  <h1>Hello {{ name }}, Welcome Onboard</h1>
  <table border="1">
    <tr>
      <td>ID</td>
      <td>NAME</td>
      <td>PHONE</td>
      <td>ADDRESS</td>
    </tr>
    <tr v-for="item in restaurant" :key="item.id">
      <td>{{ item.id }}</td>
      <td>{{ item.name }}</td>
      <td>{{ item.contact }}</td>
      <td>{{ item.address }}</td>
    </tr>
  </table>
</template>
<script>
import Header from "./Header.vue";
import axios from "axios";
export default {
  /* eslint-disable */ name: "Home",
  data() {
    return {
      name: "",
      restaurant: [],
    };
  },
  components: {
    Header,
  },
  async mounted() {
    let user = localStorage.getItem("user-info");
    this.name = JSON.parse(user).name;
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
    let result = await axios.get("http://localhost:3000/restaurants");
    console.warn(result);
    this.restaurant = result.data;
  },
};
</script>
<style>
h1 {
  text-align: center;
}

tr:first-child td {
  font-weight: 600;
}

td {
  text-align: center;
  width: 160px;
  height: 40px;
}
</style>