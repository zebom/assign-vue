

<template>
  <div class="container">
    <h1>Forgot Password</h1>
    <form @submit.prevent="forgotPassword">
      <div class="form-group">
        <input class="form-control" type="email" placeholder="Enter your email" v-model="email">
      </div>
      <div class="form-group">
        <button class="btn btn-primary" type="submit">Reset Password</button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";
import axios from "axios";

const email = ref('');

const forgotPassword = async () => {
  try {
    const response = await axios.post('http://localhost:4000/forgot-password', { email: email.value });
    
    alert(response.data.message);
  } catch (error) {
    console.error(error);
    alert('An error occurred. Please try again later.');
  }
}
</script>

<style scoped>
.container {
  margin-top: 50px;
  text-align: center;
}
.form-group {
  margin-bottom: 20px;
}
</style> 