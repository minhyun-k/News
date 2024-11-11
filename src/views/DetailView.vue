<template lang="">
    <div class="detail">
        <div class="title">
            <h1>{{$route.query.title}}</h1>
            <div class="newsImg">
                <img class="img" :src="$route.query.image_url"/>
            </div>
            <p>{{$route.query.summary}}</p>

        </div>
    </div>
</template>
<script>
export default {
    name:"DetailView",
    mounted(){
        console.log(this.$route.query)
    }
}
</script>
<style lang="scss">
.detail{
    max-width: 390px;
}
    .newsImg{
        .img{
            width: 100%;

        }
    }
</style>