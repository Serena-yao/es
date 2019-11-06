<template>
    <div>
        详情页面
        <h2>{{info.title}}</h2>
        <p>{{info.time}}</p>
        <img :src="info.banner" alt="">
        <p>{{`${info.favor} 赞同 ${info.comment} 评论`}} </p>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data() {
        return {
            info:{}
        }
    },
    async created(){
        let id=this.$route.params.id;
        let data=await axios.get(`/api/detail?id=${id}`)
        this.info=data.data;
    }
}
</script>
