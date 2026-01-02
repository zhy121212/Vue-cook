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

            
        </div>
        <div>body-right</div>
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
        gap: 100px;
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