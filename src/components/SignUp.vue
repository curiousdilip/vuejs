<template>
    <div class="signup">
        <img class="logo" src="../assets/logo.svg" />
        <h1> Sign Up</h1>
        <div class="register">
            <input type="text" v-model="name" placeholder="Enter Name">
            <input type="email" v-model="email" placeholder="Enter Email">
            <input type="password" v-model="password" placeholder="Enter Password">
            <button v-on:click="signUp">Sign Up</button>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'SignUp',
    data() {
        return {
            name: '', email: '', password: ''
        }
    },

    methods: {
        async signUp() {
            console.warn("signUp", this.name, this.password, this.email)
            let result = await axios.post("http://localhost:3000/users", {
                email: this.email, name: this.name, password: this.password,
            });
            console.warn(result)
            if (result.status == 201) {
                alert("sign up Done")
            }
            localStorage.setItem("user-info", JSON.stringify(result.data))
        }
    }
}
</script>

<style>
.signup {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    height: 80vh;
}

.logo {
    width: 100px;
}


.register input {
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

.register button {
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

.register button:hover {
    background-color: white;
    color: orange;
    border: 1px solid orange;
}
</style>