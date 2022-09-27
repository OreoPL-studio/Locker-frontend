<script setup>
import router from '../router';
</script>

<template>
    <div class="error-component">
        <h1>Oops!</h1>
        <h3>The route you tried to navigate to doesn't exist.</h3>
        <img src="public\error.png">
        Go back to <router-link to="/login">Login </router-link> or<router-link to="/register">Register </router-link>
    </div>
</template>