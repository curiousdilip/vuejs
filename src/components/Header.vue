<template>
  <div class="nav">
    <a href="#">Home</a>
    <a href="#">Add Restaurant</a>
    <a href="#">Update Restaurant</a>
    <a href="#">Logout</a>
  </div>
</template>

<script>
export default {
  /* eslint-disable */ name: "Header",
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