<script setup>
    import router from '../router';
    
        const login = ''
        const password = ''
    
        function onSubmit(e){
            e.preventDefault()
    
            /*if(!login || !password ){
                alert('Please fill the form')
                return
            }else{*/
                router.push('/home')
            //}
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