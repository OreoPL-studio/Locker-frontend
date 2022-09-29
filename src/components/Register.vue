<script setup>
    import router from '../router';
    import { ref } from 'vue';
    
        const login = ref('')
        const password = ref('')
    
        async function onSubmit(e){
            localStorage.setItem("login", login.value);
            localStorage.setItem("password", password.value);

            const options = {method: 'GET', headers: {Authorization: 'Basic dXNlcjpwYXNzd29yZA=='}};
            const response = await fetch('http://localhost:3000/auth', options);
            
            e.preventDefault()

            if(response.status == 200){
                router.push('/home')
            }else{
                router.push('/error')
            }
        }
    
    </script>
    
    <template>
        <div class="register-component">
            <div class="register-child">
                <h1>Nice to meet you!</h1>
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
    
    <style scoped>
    
    </style>