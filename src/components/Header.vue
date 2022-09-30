<script setup>
import { def } from "@vue/shared";
import { defineProps, reactive } from "vue";
import Login from './Login.vue'

const login = localStorage.getItem("login");

</script>

<template>
    <div class="header">
        <img src="avatar.png">
        <router-link to="/"><i class="fa-solid fa-arrow-right-from-bracket"></i></router-link>
    </div>
    <p class="hi">Hi {{login}}</p>
</template>