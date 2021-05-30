<template>
  <router-view />
</template>

<script>

export default {
  name: 'App',
  components: {

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body{
  margin:0px;
  padding:0px;
}

.logo{
    width:100px;
}

.register input, .login input{
    width: 300px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-left: auto;
    margin-right: auto;
    border: 1px solid lightseagreen;
}

.register button, .login button{
    width: 320px;
    height: 40px;
    border: 1px solid lightseagreen;
    background: darkolivegreen;
    color: #fff;
    cursor: pointer;
}
</style>
