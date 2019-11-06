<template>
    <div class="page">
        <ul v-for="item in list" :key="item">
            <div class="inside" @click="btnclick(item)">
                <h3>{{item.title}}</h3>
                <dl>
                    <dd class="oy">{{item.description}}</dd>
                    <dt><img :src="item.banner" alt=""></dt>
                </dl>
                <div class="user">
                    <p>{{item.comment}} 赞同</p>
                    <p>{{item.favor}} 评论</p>
                </div>
            </div>
            
        </ul>
    </div>
</template>
<script>
import axios from 'axios';
export default {
    data() {
        return {
            page:1,
            pageSize:10,
            type:'',
            list:[]
        }
    },
    watch:{
        $route:function(){
            this.type=this.$route.params['type'];
            this.getData();
        }
    },
    methods: {
        async getData(){
        let data=await axios.get(`/api/list?type=${this.type}&page=${this.page}&pageSize=10`)
        console.log('router',data)
        this.list=data.data
    },
    btnclick(item){
        // alert('1')
        // console.log(this)
        this.$router.push({
            path:`/detail/${item.id}`
        })
    }
    },
    mounted() {
        this.type=this.$route.params['type'];
        this.getData();
    },
}
</script>
<style lang="scss" scoped>
    *{
        list-style-type: none;
        padding:0;
        margin:0;
    }
    .page{
        flex:1;
        overflow: auto;
    }
    .inside{
        width:100%;
        height: 3rem;
        border:.01rem solid #ccc;
        h3{
            width:100%;
            height: .5rem;
            // background: #ccc;
            margin-left: -1.7rem;
        }
        dl{
            width:100%;
            display: flex;
        }
    }
    .oy{
        display:-webkit-box;
        overflow: hidden;
        text-overflow:ellipsis;
        color:#666;
        -webkit-line-clamp: 4;
        -webkit-box-orient:vertical;
        height: 1.74rem;
    }
    .user{
        width:100%;
        height: .5rem;
        display: flex;
        p{
            padding-left: .3rem;
        }
    }
</style>
