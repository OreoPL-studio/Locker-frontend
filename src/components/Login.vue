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
        <div class="login-component">
            <div class="login-child">
                <h1>Hi there</h1>
                <h3>We're so happy to see you again!</h3>
    
                    <form @submit="onSubmit" class="login-form">
                        <p>
                            <input type="text" v-model="login" name="login" placeholder="Login" required>
                        </p>
                        <p>
                            <input type="text" v-model="password" name="password" placeholder="Password" required>
                        </p>
                        <button type="submit">
                            Login
                        </button>
                    </form>
                
                <p>First time? <router-link to="/register">Register</router-link></p>
            </div>
        </div>
    </template>