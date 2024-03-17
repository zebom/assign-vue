<script setup>

</script>

<template>

<div class="nav">
  <RouterLink class="nav-item" to="/">Home</RouterLink>
  <RouterLink class="nav-item" to="/about">About</RouterLink>
  <RouterLink class="nav-item" to="">Services</RouterLink>
  <RouterLink class="nav-item" to="">Contact us</RouterLink>
  <RouterLink class="nav-item" to="/login">Login</RouterLink>
  <RouterLink class="nav-item" to="/signup">SignUp</RouterLink>

  
</div>
<RouterView/>


</template>

<style scoped>

.nav{
  background-color: green;
  padding: 28px 0px;
}
.nav .nav-item{
  text-decoration: none;
  padding: 0px 14px;
  color: white;
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
}
</style>

<!-- its the parent component  -->