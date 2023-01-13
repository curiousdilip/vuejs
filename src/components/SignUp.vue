<template>
    <img class="logo" src="../assets/logo.svg" />
    <h1> Sign Up</h1>
    <div class="register">
        <input type="text" v-model="name" placeholder="Enter Name">
        <input type="email" v-model="email" placeholder="Enter Email">
        <input type="password" v-model="password" placeholder="Enter Password">
        <button v-on:click="signUp">Sign Up</button>
    </div>
</template>

<script>
export default {
    name: 'SignUp',
    data() {
        return {
            name: '', email: '', password: ''
        }
    },

    methods: {
        signUp() {
            console.warn("signUp", this.name, this.password, this.email)
        }
    }
}
</script>

<style>
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