<template>
<div class="modal fade"  id="staticRegister" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1" aria-hidden="true" >
<div class="modal-dialog modal-dialog-centered">
<div class="modal-content">
  <h3 class="text-center pt-3 pb-3">注册</h3>
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
<div class="input-group  input-group-sm">
    <label for="confirmPassword" class="px-2"> 确认密码： </label>
    <input type="Password" class="form-control me-5" v-model="confirmPassword" >
</div>
<div class="container" style="height: 20px;">
    <p style="font-size: smaller;color: red; padding-left: 19%;" v-if="confirmPasswordNull">请再次输入密码</p>  
    <p style="font-size: smaller;color: red; padding-left: 19%;" v-else-if="confirmPasswordError">密码不一致</p>  
</div>
<div class="pt-2 container-fluid d-grid">
    <div class="row pb-3">
        <div class="col-2"></div>
        <button type="button" class="btn btn-primary col-2 ms-4" @click="register">注册</button>
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
            confirmPassword: '',
            usernameNull: false,
            passwordNull: false,
            confirmPasswordNull: false,
            confirmPasswordError: false
        };
    },
    methods:{
        reset(){
            this.username='',
            this.password='',
            this.confirmPassword='',
            this.usernameNull= false,
            this.passwordNull= false,
            this.confirmPasswordNull= false,
            this.confirmPasswordError= false
        },
        register(){
            if((this.username != '' && this.password != '' && this.confirmPassword != '') && (this.password == this.confirmPassword)){
            axios.post('http://localhost:8080',{
                username: this.username,
                password: this.password
            })
            .then(response =>{
                if(response.data==1){
                    console.log("用户名重复")
                }else{
                    console.log("登录成功")
                }
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
            if(this.confirmPassword == ''){
                this.confirmPasswordNull=true
            }else{this.confirmPasswordNull=false}
            if(this.password != this.confirmPassword){
                this.confirmPasswordError=true
            }else{this.confirmPasswordError=false}
        }
    }
};
</script>