<template>
    <headers class="headerc">
        <span class="logo">下厨房</span>
        <div class="search-warpper">
            <input class="search" type="text" placeholder="搜索菜谱, 食材">
            <span class="search-text">搜索</span>
        </div>
        
        <span>首页</span>
        <span>菜谱分类</span>
        <span>菜单</span>
        <span>注册</span>
        <span>登录</span>
    </headers>
    
</template>

<style scoped>
.headerc {
    display: flex; 
  text-align:center;
  align-items: center;  
  justify-content: center;
  height: 65px;
  background: #fff;
  gap: 80px;
  font-size: large;
   border-bottom: 1px solid rgba(0,0,0,0.06); /* 很浅的线 */
}
.logo{
    color: lab(85.75% -7.4 85.15 / 0.996);
    font-size: xx-large;
}
.search{
    height: 40px;
    width: 200px;
    /* border: 1px solid rgba(0, 0, 0, 0.06); */
      border: none;
   box-shadow: inset 0 0 0 1px rgba(0, 0, 0, 0.06);
    font-size: large;
     outline: none; 
}
.search-warpper{
    height: 40px;
    display: flex;
    align-items: center;
    gap: 0px; /* 搜索框和文字间距，可调 */
    /* width: 240px; */
    background-color: #eba50ed6;
    
}
.search-text{
    width: 60px;
}
</style>

