<script setup>
import router from '../router';
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'

function onSumbit(){
    console.log(1)
}
</script>

<template>
        <Header/>
        <p>Your device</p>
        <div class="lockerButtonsSection">
            <img src="whiteBox.png" class="white-box-home">
            <i class="fa-solid fa-lock"></i>
            <div class="buttons">
                <button class="btn1">Unlock</button>
                <button class="btn2">Enable</button>
                <button class="btn3">Disable</button>
            </div>
        </div>
        <p>Logs</p>
        <Footer/>
</template>