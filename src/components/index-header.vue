<template>
    <div class="top">
        <div class="top-left">
            <span>下</span>
            <span>厨</span>
            <span>房</span>
        </div>
        <div class="top-mid">
            <div class="top-mid-left">
                <input type="text" placeholder="搜索菜谱, 食材" v-model="searchQuery">
                <input type="submit" value="搜菜谱">
            </div>
            <div class="top-mid-right">
                <a href="">首页</a>
                <a href="">菜谱分类</a>
                <a href="">菜单</a>
                <a href="">作品动态</a>
            </div>
        </div>

        <div class="top-right">
            <a href="">登录</a>
            <a href="">注册</a>
        </div>
    </div>

</template>

<style scoped>
    .top{
        width: auto;
        height: 105px;
        display: flex;
        gap: 150px;
        justify-content: center;
        align-items: center;
        /* background-color: #8bcfdb; */
    }
    .top-left{
        /* color: rgb(236, 136, 14); */
        font-size: xx-large;
        font-weight: bolder;
        display: flex;
        gap: 1px;
    }
    .top-left span:nth-of-type(1){
        color: #8bcfdb;
    }
    .top-left span:nth-of-type(2){
        color: #df2d2b;
    }
    .top-left span:nth-of-type(3){
        color: #f7805a;
    }
    /* .top-mid-left{
        display: flex;
        gap: 2px;
        
    } */
     .top-mid{
        display: flex;
        gap: 10px;
     }
     .top-mid-left input:first-child{
        border: 1px solid #f0f0f0;
        outline: none;
        
    }
    .top-mid-left input:last-child{
        background-color: #dd3915;
        color: white;
        border: none;
    }
    .top-mid-right {
        display: flex;
        gap: 10px;
    }
    .top-mid-right a{
        color: #e0603c;
    }
    .top-right{
        display: flex;
        gap: 10px; 
    }
    .top-right a{
        color: #e0603c;
    }
</style>

<script setup>
import { ref } from 'vue';
const searchQuery = ref('')
</script>