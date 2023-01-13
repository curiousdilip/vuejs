<template>
    <h1>Hello, Welcome Onboard</h1>
</template>
<script>
export default {/* eslint-disable */
    name: "Home",
    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: 'SignUp' })
        }
    }
};
</script>
<style>
h1 {
    text-align: center;
}
</style>