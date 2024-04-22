<template >
<body>
    <div class="backpicture">
        <div class="pt-2 container d-flex">
            <img src="../assets/images/logo-white.svg" class="img-fluid" alt="logo">
            <div class="ms-auto btn btn-outline-light" data-bs-toggle="modal" data-bs-target="#staticLogin">登录</div>
            <div class="ms-2 btn btn-outline-light"  data-bs-toggle="modal" data-bs-target="#staticRegister">注册</div>
        </div>
        <div class="p-4 container text-center text-light">
            <h1>云端编程，浏览器里边学边练</h1>
            <p class="mt-3 fs-5">软件定义一切，网络连接时空，学习软件技术，创造未来世界</p>
            <button
                @click="hint"
                class="mb-2 btn btn-outline-light bg-body text-primary mt-3 px-5">马上学习</button>
        </div>
    </div>
    <Register></Register>
    <Login></Login>
</body>
</template>
<script>
import Register from "./Register.vue";
import Login from "./Login.vue";

export default{
    components:{
        Register,
        Login
    },
    methods:{
        hint(){
            confirm("请先登录账号");
        }
    }
}
</script>
<style>
        .backpicture {
            background: url(../assets/images/home-banner@2x.jpg) no-repeat;
            background-size: 100% 100%;
        }
</style>