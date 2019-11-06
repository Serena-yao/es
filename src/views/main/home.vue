<template>
    <div class="three">
        <div class="nav-three">
            <router-link class="active" to="/main/home/attention">关注</router-link>
            <router-link class="active" to="/main/home/recommend">推荐</router-link>
            <router-link class="active" to="/main/home/hot">热门</router-link>
        </div>
        
        <div class="main">
            <router-view></router-view>
        </div>
        <div class="footer"></div>
        
    </div>
</template>
<style lang="scss" scoped>
    .three{
        width:100%;
        height: 100%;
        display: flex;
        flex-direction: column;
    }
    .nav-three{
        width:100%;
        height: .5rem;
        line-height: .5rem;
        border-bottom: .01rem solid #ccc;
        display: flex;
        justify-content: space-around;
    }
    .active{
        text-decoration: none;
    }
    .active.router-link-active{
        color:palevioletred;
    }
</style>
