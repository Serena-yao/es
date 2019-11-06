<template>
    <div class="main">
        <div class="head"></div>
        <div class="main-m">
            <router-view></router-view>
        </div>
        <div class="nav-two">
            <router-link class="active" to="/main/home">首页</router-link>
            <router-link class="active" to="/main/idea">想法</router-link>
            <router-link class="active" to="/main/edu">大学</router-link>
            <router-link class="active" to="/main/message">消息</router-link>
            <router-link class="active" to="/main/my">我的</router-link>
        </div>
    </div>
</template>
<style lang="scss" scoped>
*{
    font-size: .32rem;
}
.main{
    width:100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    .head{
        width:100%;
        height: .3rem;
        background: #ccc;
    }
    .main-m{
        width:100%;
        flex:1;
        overflow: auto;
        }
    .nav-two{
        width:100%;
        height: .8rem;
        line-height: .8rem;
        display: flex;
        justify-content: space-around;
        position: fixed;
        bottom:0rem;
        background: #fff;
        border-top: .01rem solid #ccc;
    }
}
    .active{
        text-decoration: none;
    }
    .active.router-link-active{
        color:palegreen;
    }
</style>
