<template>
    <img class="logo" src="../assets/resto-logo.jpg" />
    <h1>Sign Up</h1>
    <div class="register">
        <input type="text" v-model="signup.name" placeholder="Enter the Name" />
        <input type="email" v-model="signup.email" placeholder="Enter the Email" />
        <input type="password" v-model="signup.password" placeholder="Enter the Password" />
        <input type="tel" v-model="signup.contact" placeholder="Enter the Contact Number" />

        <button v-on:click="signUp">Sign Up</button>
    </div>
    <p><router-link to="/login">Login</router-link></p>
</template>

<script>
    import axios from 'axios'

    export default{
        name:"Signup",

        data(){
            return{
                response:"", 
                signup:{
                    name:"",
                    email:"",
                    password:"",
                    contact:""
                }
            }
        },

        methods:{
            // async signUp(){
            //     let result = await axios.post("http://localhost:3000/users",this.signup)
            //     console.log(result)

            //     if(result.status == 201){
            //         alert("User Registered successfully")
            //         localStorage.setItem("user-info",JSON.stringify(result.data))
            //     }
            // }

            signUp(){
                axios.post("http://localhost:3000/users",this.signup)
                     .then(result => {this.response=result})
                if(this.response.status == 201){
                    localStorage.setItem("user-info",JSON.stringify(this.response.data))
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