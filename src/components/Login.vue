<template>
<div class="modal fade"  id="staticLogin" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1" aria-hidden="true" >
<div class="modal-dialog modal-dialog-centered">
<div class="modal-content">
    <h3 class="text-center pt-3 pb-3">登录</h3>
<div class="input-group  input-group-sm">
    <label for="username" class="px-3"> 用户名： </label>
    <input type="text" class="form-control me-5" v-model="username" >
</div>
<div class="container" style="height: 20px;">
    <p style="font-size: smaller;color: red; padding-left: 19%;" v-if="usernameNull">用户名不能为空</p>  
</div>
<div class="input-group input-group-sm">
    <label for="password" class="px-4"> 密码： </label>
    <input type="password" class="form-control me-5" v-model="password" >
</div>
<div class="container" style="height: 20px;">
    <p style="font-size: smaller;color: red; padding-left: 19%;" v-if="passwordNull">请输入密码</p>  
</div>
<div class="pt-2 container-fluid d-grid">
    <div class="row pb-3">
        <div class="col-2"></div>
        <button type="button" class="btn btn-primary col-2 ms-4" @click="Login">登录</button>
        <button type="button" class="btn btn-outline-secondary col-2 ms-3" @click="reset">重置</button>
        <button type="button" class="btn btn-outline-secondary col-2 ms-3" @click="reset" data-bs-dismiss="modal">返回</button>
        <div class="col-3"></div>
    </div>
</div>
</div>
</div>
</div>
</template>

<script>
import axios from 'axios';

export default{
    data(){
        return{
            username: '',
            password: '',
            usernameNull: false,
            passwordNull: false,
        };
    },
    methods:{
        reset(){
            this.username='',
            this.password='',
            this.usernameNull= false,
            this.passwordNull= false
        },
        Login(){
            if(this.username != '' && this.password != ''){
            axios.post('http://localhost:8080/Users/Login',{
                username: this.username,
                password: this.password
            })
            .then(response =>{
                console.log(response.data);
            })
            .catch(error => {
                console.log(error);
            });
            }
            if(this.username == ''){
                this.usernameNull=true
            }else{this.usernameNull=false}
            if(this.password == ''){
                this.passwordNull=true
            }else{this.passwordNull=false}
        }
    }
}
</script>