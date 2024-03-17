
  <script setup>
import { ref } from "vue";
import axios from "axios";
import 'bootstrap/dist/css/bootstrap.min.css';

const Username = ref('');
const email = ref('');
const password = ref('');

const signup = async () => {
    console.log(`${Username.value} ${email.value} ${password.value}`);
    try {
        const response = await axios.post('http://localhost:4000/user',{
            username: Username.value,
            email: email.value,
            password: password.value
        });
        console.log(response.data); 
    } catch (error) {
        console.error(error); 
    }
}
</script>

<template>
<div class="container">
    <h1>Signup Here</h1>
    <form @submit.prevent="signup">

        <div class="sign-form">
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
                <button class="btn btn-primary" type="submit">Signup</button>
            </div>
        </div>
    </form>
    <p>{{ Username }}</p>
</div>
</template>

<style scoped>
.sign-form {
    background-color: rgb(191 191 220);
    width: 50%;
    border-radius: 10px;
    padding: 2% 1%; 
}
.sign-form .form-group {
    margin-bottom: 1% ;
}
.sign-form .form-input {
    border-style: none;
    padding-top: 5px 28px;
}
</style>
