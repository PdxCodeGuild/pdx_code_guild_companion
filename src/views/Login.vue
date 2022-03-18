<script setup>
    import {ref} from 'vue'

    const email = ref('')
    const password = ref('')

    const loginUser = () => {
        fetch('http://localhost:8000/users/login/', {
            method: "POST",
            headers: {
                'Content-Type': 'Application/json'
            },
            body: JSON.stringify({
                email: email.value,
                password: password.value
            })
        }).then(res => console.log(res))
    }
</script>

<template>
<h1>Login</h1>
<form action="" @submit.prevent="loginUser">
    <label for="email">Email:</label>
    <input id="email" type="email" placeholder="someone@pdxcodeguild.com" autocomplete="off">
    <label for="password">Password:</label>
    <input id="password" type="password" placeholder="&bull;&bull;&bull;&bull;&bull;&bull;">
    <button type="submit">Login</button>
</form>
</template>

<style>

</style>