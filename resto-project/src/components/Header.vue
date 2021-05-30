<template>
  <div class="nav">
    <a href="#">Home</a>
    <a href="#">About Us</a>
    <a href="#">Users</a>
    <a href="#">Logout</a>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.nav{
  background-color: lightseagreen;
  overflow: hidden;
}

.nav a{
  text-align: center;
  text-decoration: none;
  padding: 10px;
  float: left;
  font-size: 20px;
  margin-right: 10px;
  color: #fff;
}

.nav a:hover{
  background: darkolivegreen;
  color: blanchedalmond;
}

</style>