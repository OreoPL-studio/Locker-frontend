<script setup>
import router from '../router';

    const login = ''
    const password = ''

    function onSubmit(e){
        e.preventDefault()

        /*if(login || password ){
            alert('Please fill the form')
            return
        }else{*/
            router.push('/home')
        //}
    }

</script>

<template>
    <div class="register-component">
        <div class="register-child">
            <h1>Nice to</h1>
            <h1>meet you!</h1>
            <h3>Ready to join us?</h3>

                <form @submit="onSubmit" class="login-form">
                    <p>
                        <input type="text" v-model="login" name="login" placeholder="Login" required>
                    </p>
                    <p>
                        <input type="text" v-model="password" name="password" placeholder="Password" required>
                    </p>
                    <div class="termsOfService">
                        <input type="checkbox" required>
                        Yes, I agree with Terms and Policy
                    </div>
                    <button type="submit">
                        Register
                    </button>
                </form>
            
            <p>Have an account? <router-link to="/login">Login</router-link></p>
        </div>
    </div>
</template>