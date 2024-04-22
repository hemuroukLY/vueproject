<template >
<div class="backcolor">
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <img src="../assets/images/img-lab@2x.png" alt="first" class="img-fluid">
            </div>
            <div class="col-md-12 mt-5 mb-5">
                <h2 class="mt-2"><strong>高级web编程实验室</strong></h2>
                <p class="mt-3 text-justify">每人拥有自己完全独立的编程实验室，内置所有基础软件及学习素材，打开浏览器，即刻开始编程！</p>
                <button @click="hint"
                class="btn btntext btn-outline-dark col-12 text-muted text-center">了解详情</button>
            </div>
        </div>
    </div>
</div>
<div class="container">
        <div class="row  mt-5 ">
            <div class="col-md-12 ">
                <img src="../assets/images/img-screens@2x.png" alt="second" class="img-fluid">
            </div>
            <div class="col-md-12 mt-5">
                <h2><strong>双屏学习</strong></h2>
                <p class=" text-justify">双屏学习，小屏视频互动操作，学习无障碍，打开浏览器，即可开始编程！</p>
                <button @click="hint"
                class="btn btntext btn-outline-dark col-12 text-center" >了解详情</button>
            </div>
        </div>
    </div>
</template>
<script>
export default{
    methods:{
        hint(){
            confirm("请先登录账号");
        }
    }
}
</script>

<style>
.backcolor{
            background-color: #f4f4f4;
        }
 .btntext:hover {
            color: white !important;
        }
</style>