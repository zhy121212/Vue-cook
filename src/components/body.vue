<template>
    <body class="body-area">
        <div class="left-area">
            <ul>
                <li class='li-text' v-for="i in category_list">
                    <i class="iconfont icon-mifan"></i>&nbsp;&nbsp;&nbsp;&nbsp;{{i}}</li>
            </ul>
            <p class="red">全部菜谱分类</p>
        </div>

        <div class="mid-area">
<div class="mid-up">
    <div class="slider">
        <img 
            v-for="(img, index) in images" 
            :key="index" 
            :src="img" 
            :class="{ active: currentIndex === index }"
        >
    </div>
    <p class='pre-fonts'>新秀菜谱</p>
    <p class='pre-fonts'>最新流行</p>
</div>

            </div>
            

        <div class="right-area">
            <div class="login">
                <div class="red-fill">
                    <p class="white">QQ登录</p>
                </div>
                <div class="red-fill">
                    <p class="white">微博登录</p>
                </div>
                               
            </div>
            <!-- <p>我是右边区域</p> -->
             <div class="rank">
                <p class="pre-fonts">流行搜索</p>
                <ol class="rank-1">
                    <li>1&nbsp;&nbsp;&nbsp;&nbsp;家常菜</li>
                    <li>2&nbsp;&nbsp;&nbsp;&nbsp;红烧肉</li>
                    <li>3&nbsp;&nbsp;&nbsp;&nbsp;可乐鸡翅</li>
                    <li>4&nbsp;&nbsp;&nbsp;&nbsp;排骨</li>
                </ol>
             </div>
             <div>
                <p class="pre-fonts">流行菜单</p>
             </div>

        </div>
        
    </body>
</template>
<script setup>
import { ref } from 'vue';

const category_list = ref([
  '家常菜', '快手菜', '下饭菜', '早餐', '肉', '鱼', '蔬菜', '...'
])

const images = ref([
  '/static/1.png',
  '/static/2.png',
  '/static/3.png'
]);

// --- 新增逻辑 ---
const currentIndex = ref(0);

// 最简单的执行方式：直接在顶层每 3 秒切换一次索引
setInterval(() => {
  currentIndex.value = (currentIndex.value + 1) % images.value.length;
}, 3000);
// ---------------
</script>
<style>
.body-area{
    display: flex;
    justify-content: center;
    align-items: flex-start; 
    gap: 40px;
}
.left-area{
    width: 200px;
    background-color: antiquewhite;
}
.right-area{
    width: 380px;
    /* background-color: rgb(237, 139, 10); */
    display: flex;
    gap: 10px;
    flex-direction: column;
    
}
.mid-area{
    width: 650px;
    /* background-color: aqua; */
}
.li-text{
    line-height: 40px;
}
.red{
    color: brown;
}
img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
      animation: slide 6s infinite linear;
}


.login{
    height: 320px;
    width: 380px;
      display: flex;
        flex-direction: column;
  justify-content: center; /* 水平居中 */
  align-items: center;     /* 垂直居中 */
  gap: 10px;
  background-color: #f7f7f7;
}
.rank{    
    width: 380px;
    background-color: #fff;
}
.pre-fonts{
    font-size: large;
    color: rgb(195, 118, 24);
    font-weight: bold;
}
.rank-1{
    display: flex;
    gap: 10px;
    flex-direction: column;
}
ul,ol{
    list-style: none;
    padding: 0;
    margin: 0;
}
.iconfont {
  color: rgb(28, 10, 233);      /* 图标颜色 */
  font-size: 32px; /* 图标大小 */
}
.red-fill{
    width: 185px;
    height: 55px;
    background-color: rgba(199, 20, 8, 0.977);
    display: flex;
    justify-content: center;
    align-content: center;
}
.white{
    color: #f7f7f7;

}

.mid-up {
  width: 650px;
  height: 320px;
  overflow: hidden;
  position: relative;
}

/* 1. 确保父容器有高度且定位 */
.slider {
  position: relative;
  width: 100%;
  height: 320px; /* 建议和 .mid-up 高度一致 */
  overflow: hidden;
  border-radius: 8px;
}

/* 2. 所有图片默认重叠在一起，且透明 */
.slider img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  transition: opacity 1s ease-in-out; /* 淡入淡出时长 */
}

/* 3. 只有 active 的图片才显示 */
.slider img.active {
  opacity: 1;
  z-index: 1;
}
</style>