
<script setup>
import { ref } from "vue";
import axios from "axios";
import 'bootstrap/dist/css/bootstrap.min.css'; // Import Bootstrap CSS

const Username = ref('');
const email = ref('');
const password = ref('');

const login = async () => {
    console.log(`${Username.value} ${email.value} ${password.value}`);
    try {
        const response = await axios.post('http://localhost:4000/user/login',{
            username: Username.value,
            email: email.value,
            password: password.value
        });
        console.log(response.data); // Log response data if needed
        alert('logged in succesfylly');
        window.location.href = '/about';
       } catch (error) {
        console.error(error); // Log any errors
    }
}
</script>

<template>
<div class="container">
    <h1>login Here</h1>
    <form @submit.prevent="login">

        <div class="login-form">
            <div class="form-group">
                <input class="form-control" type="text" placeholder="Enter Username" v-model="Username">
            </div>
            <div class="form-group">
                <input class="form-control" type="email" placeholder="Enter Email" v-model="email">
            </div>
            <div class="form-group">
                <input class="form-control" type="password" placeholder="Enter Password" v-model="password">
            </div>
            <div class="form-group">
                <button class="btn btn-primary" type="submit">login</button>
            </div>
        </div>
    </form>
    <!-- <p>{{ Username }}</p> -->
</div>
</template>

<style scoped>
.login-form {
    background-color: rgb(191 191 220);
    width: 50%;
    border-radius: 10px;
    padding: 2% 1%; 
}
.login-form .form-group {
    margin-bottom: 1% ;
}
.login-form .form-input {
    border-style: none;
    padding-top: 5px 28px;
}
</style>