<template>
    <div class="body">
        <div class="body-left">
            <ul>
                <li v-for="value in category_list">
                    <a href="#">{{ value }}</a>
                </li>
            </ul>
            <a href="#">全部菜谱分类</a>
        </div>

        <div class="body-mid">
            <div class='body-mid-top'>
                <div class="slide" :style="slideStyle">
                    <img src="/static/1.png" alt="">
                    <img src="/static/2.png" alt="">
                    <img src="/static/3.png" alt="">
                </div>
            </div>
            <div class="body-mid-mid">
                <div class="subtitle-layout">
                    <a class="subtitle" href="">新秀菜谱</a>
                    <a href="">全部</a>
                </div>
                <div class="body-mid-mid-detail-img-and-describe">
                    <div class="body-mid-mid-detail">
                        <img src="/static/1/1.png" alt="">
                        <a href="">荔浦芋头褒</a>
                    </div>
                    <div class="body-mid-mid-detail">
                        <img src="/static/1/2.png" alt="">
                        <a href="">玉米面饼</a>
                    </div>

                </div>

            </div>
            <div class="body-mid-down">
                <div class="subtitle-layout">
                    <a class="subtitle" href="">最近流行</a>
                    <a href="">全部</a>
            </div>

            </div>

            
        </div>
        <div class="body-right">
            <div class='body-right-top'>
                <div class='body-right-top-login'>
                    <a href="">QQ登录</a>
                    <a href="">微博登录</a>
                </div>
            </div>
        </div>
    </div>

    <div></div>
    <div></div>
    <div></div>
</template>

<style scoped>
    .body{
        display: flex;
        justify-content: center;
        /* align-items: center; */
        gap: 60px;
    }
    
    .body-left ul{
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10px;
        flex-direction: column;
    }
    .body-left ul li{
        list-style: none;
    }
    .body-mid{
        width: 730px;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    .body-mid-top{
        height: 400px;
        overflow: hidden;
    }
    /* .body-mid-top img{
        height: 100%;
        width: 100%;
        object-fit: cover;
    } */
    .slide{
        display: flex;
        height: 100%;
        transition: transform 0.6s ease;
    }
    .slide img{
        width: 730px;
        height: 100%;
        object-fit: cover;
        flex-shrink: 0;
    }
    
    .body-mid-mid-detail{
        width: 200px;
        /* height: 100px; */
        display: flex;
        flex-direction: column;
        gap: 20px;
    }
    .body-mid-mid-detail img{
        object-fit: cover;
        height: 100%;
    }
    .body-mid-mid{
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    .body-mid-mid-detail-img-and-describe{
        display: flex;
        gap: 10px;
    }
    .body-mid-mid-detail a{
        text-align: center;
    }
    .subtitle-layout{
        display: flex;
        gap: 15px;
    }
    .body-right{
        width: 300px;
        
    }
    .body-right-top{
        height: 300px;
        background-color: whitesmoke;

    }
    .body-right-top-login{
        height: 100%;
        /* background-color: blue; */
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 20px;
    }
</style>

<script setup>
    import { ref , computed, onMounted, onUnmounted} from 'vue';
    

    const category_list = ref(
        ['家常菜', '快手菜', '下饭菜', '早餐', '肉', '鱼', '...']
    )
    const current = ref(0)
    const total = 3
    const slideStyle = computed(
        () =>{
            return{
                transform:`translateX(-${current.value * 730}px)`
            }
        }
    )
    let timer = null
    onMounted(
        ()=>{
            timer = setInterval(()=>{
                current.value = (current.value + 1)%total
            }, 3000)
        }
    )
    onUnmounted(
        ()=>{
            clearInterval(timer)
        }
    )
</script>