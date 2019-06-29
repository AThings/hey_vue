<template>
    <div>
        <h1>请登录</h1>
        用户名：<input type="text" v-model="username"/>
        密码：<input type="password" v-model="password"/>
        <button @click="login">登录</button>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            username:"",
            password:"",
            publicPath: process.env.BASE_URL,
            users:[]
        }
    },
    methods:{
        login(){
            window.console.log("login")
        }
    },
    created(){
        axios.get(this.publicPath+"json/users.json").then(function(response){
                window.console.log(response);
                this.users = response.data.users;
            }).catch(function(error){
                window.console.log(error);
            })
    }
}
</script>

<style scoped>

</style>

