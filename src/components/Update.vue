<template>
  <Header />
  <h1>Hello, Welcome to Update Restaurant Page</h1>
  <form action="#" class="update">
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
    <button type="button" v-on:click="addRestaurant">
      Update New Restaurant
    </button>
  </form>
</template>
<script>
import Header from "./Header.vue";
export default {
  /* eslint-disable */ name: "Update",
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

.update input {
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

.update button {
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

.update button:hover {
  background-color: white;
  color: orange;
  border: 1px solid orange;
}
</style>