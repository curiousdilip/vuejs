<template>
  <Header />
  <h1>Hello, Welcome to Add Restaurant Page</h1>
  <form action="#" class="add">
    <input
      type="text "
      name="name"
      placeholder="Enter Name"
      v-model="restaurant.name"
    />
    <input
      type="text "
      name="address"
      placeholder="Enter Address"
      v-model="restaurant.address"
    />
    <input
      type="text "
      name="contact"
      placeholder="Enter Contact"
      v-model="restaurant.contact"
    />
    <button type="button" v-on:click="addRestaurant">Add New Restaurant</button>
  </form>
</template>
<script>
import Header from "./Header.vue";
import axios from "axios";
export default {
  /* eslint-disable */ name: "Add",
  components: {
    Header,
  },
  data() {
    return {
      restaurant: {
        name: "",
        address: "",
        contact: "",
      },
    };
  },
  methods: {
    async addRestaurant() {
      const result = await axios.post("http://localhost:3000/restaurants", {
        name: this.restaurant.name,
        address: this.restaurant.address,
        contact: this.restaurant.contact,
      });
      if (result.status == 201) {
        this.$router.push({ name: "Home" });
      }
    },
  },
  mounted() {
    let user = localStorage.getItem("user-info");
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
  },
};
</script>
<style>
h1 {
  text-align: center;
}
.add input {
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

.add button {
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

.add button:hover {
  background-color: white;
  color: orange;
  border: 1px solid orange;
}

p {
  text-align: center;
}
</style>
