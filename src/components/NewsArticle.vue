<template lang="">
    <div class="NewsList">
        <slot/>
        <div class="articleList">
            <div class="articleCard" v-for="item of data" :key="item.id">
                <router-link :to="{name:'detail', query:item}" class="articleTxt">
                    <h3>{{item.title}}</h3>
                    <span>{{item.publisher}} |</span>
                    <span>{{ pubDate(item.published_at) }}</span>
                    <!-- <p>{{item.published_at.slice(0,10)}}</p> -->
                </router-link>
                <div class="articleImg"
                :style="{backgroundImage: `url(${item.image_url})`}"
                ></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"NewsArticle",
    props: ["data", "sub"],
    methods:{
        pubDate(dateString){
            //날짜 문자열을 "YYYY-MM-DD" 형식으로 반환
            return new Date(dateString).toISOString().split('T')[0];
        }
    }

}
</script>
<style lang="scss">
    .NewsList{
        background-color: #fafafa;
        padding-top: 4px;
    }
    .articleList{
            margin: 0 20px;
            // display: grid;
            background-color: #fff;
            .articleCard{
                margin-bottom: 8px;
                border: 1px solid #ddd;
                border-radius: 8px;
                display: flex;
                justify-content: space-between;
                padding: 12px;
                gap: 15px;
                .articleTxt{
                    h3{
                        margin: 0;
                        padding: 8px 0 8px;
                        border-bottom: 1px solid #eee;
                        line-height: 28px;
                        width: 220px;
                        height: 54px;
                        text-overflow:ellipsis;
                        overflow: hidden;
                        white-space:break-word;
                        display: -webkit-box;
                        -webkit-line-clamp: 2; // 원하는 라인수
                        -webkit-box-orient: vertical
                    }
                    >span{
                        margin-top: 4px;
                        display: inline-block;
                    }
                }
                .articleImg{
                    width: 100px;
                    background-size: cover;
                    background-repeat: no-repeat;
                    border-radius: 8px;
                }
            }
        }
    .category{
        margin: 24px 40px;
        display: flex;
        justify-content: space-between;
        .categoryBtn{
            display: inline-block;
            border: 1px solid #ddd;
            border-radius: 4px;
            padding: 2px;
            font-size: 14px;
            &.active{background-color: rgba(180, 250, 152, .7);}
        }
    }
</style>