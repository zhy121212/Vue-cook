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
                <!-- 我是中上区域 -->
                <img src="/static/1.png" alt="">
                <p class='pre-fonts'>新秀菜谱</p>
                <p class='pre-fonts'>最新流行</p>

            </div>
            

        </div>

        <div class="right-area">
            <div class="login">
                <p>QQ登录</p>
                <p>微博登录</p>
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
</script>


<style scoped> 
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
    background-color: aqua;
}
.li-text{
    line-height: 40px;
}
.red{
    color: brown;
}
img {
  max-width: 100%;
  max-height: 100%;
  width: auto;
  height: auto;
  object-fit: contain;
  display: block;
  margin: auto;
}
.mid-up{
    height: 320px;
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


</style>