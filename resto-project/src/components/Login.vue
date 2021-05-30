<template>
    <img class="logo" src="../assets/resto-logo.jpg" />
    <h1>Login</h1>
    <div class="login">
        <input type="email" v-model="email" placeholder="Enter the Email" />
        <input type="password" v-model="password" placeholder="Enter the Password" />

        <button v-on:click="loginUser">Login</button>
    </div>
    <p><router-link to="/sign-up">Sign Up</router-link></p>
</template>

<script>
    import axios from 'axios'

    export default{
        name:"Login",

        data(){
            return{
                email:"",
                password:""
            }
        },

        methods:{
            async loginUser(){
                let result = await axios.get(`http://localhost:3000/users?email=${this.email}&password=${this.password}`)
            
                if(result.status == 200 && result.data.length > 0){
                    localStorage.setItem("user-info",JSON.stringify(result.data[0]))
                    this.$router.push({name:"Home"})
                } 
            }
        },

        mounted(){
            let user = localStorage.getItem("user-info")

            if(user){
               this.$router.push({name:"Home"}) 
            }
        }
    }
</script>

<style>

</style>