<template>
  <Header />
  <h1>Hello, Welcome to Update Restaurant Page</h1>
</template>
<script>
import Header from "./Header.vue";
export default {
  /* eslint-disable */ name: "Update",
  components: {
    Header,
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
</style>