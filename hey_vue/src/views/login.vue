<template>
    <div>
        <h1>请登录</h1>
        用户名：<input type="text" v-model="username"/>
        密码：<input type="password" v-model="password"/>
        <button @click="login">登录</button>
    </div>
</template>

<script>

export default {
    data(){
        return{
            username:"",
            password:""
        }
    },
    methods:{
        login(){
            axios.get("../assets/json/users.json").then(function(response){
                window.console.log(response);
            }).cacth(function(error){
                window.console.log(error);
            })
        }
    }
}
</script>

<style scoped>

</style>

