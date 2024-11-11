<template lang="">
    <div class="newsView">
        <h2>NEWS</h2>
        <nav class="buttonBox">
            <button
            @click="cate.main='articles'"
            :class="{active:cate.main=='articles'}">            
            국내
            </button>
            <button
            @click="cate.main='global-articles'"
            :class="{active:cate.main=='global-articles'}">
                해외
            </button>
        </nav>

        <div class="articleListBox">
            <NewsArticle :data="data" :sub="cate.sub">
                <div class="category">
                    <span class="categoryBtn"
                    @click="cate.sub='politics'"
                    :class="{active:cate.sub=='politics'}"
                    >
                        정치
                    </span>                    
                    <span class="categoryBtn"
                    @click="cate.sub='economy'"
                    :class="{active:cate.sub=='economy'}"
                    >
                        경제
                    </span>
                    <span class="categoryBtn"
                    @click="cate.sub='tech'"
                    :class="{active:cate.sub=='tech'}"
                    >
                        기술
                    </span>
                    <span class="categoryBtn"
                    @click="cate.sub='society'"
                    :class="{active:cate.sub=='society'}"
                    >
                        사회
                    </span>
                    <span class="categoryBtn"
                    @click="cate.sub='world'"
                    :class="{active:cate.sub=='world'}"
                    >
                        세계
                    </span>
                </div>
            </NewsArticle>
        </div>
    </div>
</template>
<script>
import NewsArticle from '@/components/NewsArticle.vue';
import axios from 'axios';

export default {
    name:'NewsView',
    data(){
        return {
            newsTitle:'국내기사',
            cate:{
                main:'articles',
                sub:''
            },
            data:[]
        }
    },
    watch: {
        cate:{
            handler(){
                this.apiRequest();
            },
            deep:true
        }
    },
    created(){
        this.apiRequest()
    },
    methods:{
        
        async apiRequest (){
            const main = this.cate.main
            const sub = this.cate.sub
            const res = await axios.get(`http://server-8dyx.vercel.app?m=${main}&s=${sub}`)

            this.data = res.data.data
            console.log(this.data)
        }
    },
    components:{
        NewsArticle
    }
}
</script>
<style lang="scss">
    .newsView{
        max-width: 390px;
        margin: 0 auto;
        .buttonBox{
            margin: 20px;
            button{
                padding: 4px 8px;
                margin: 16px;
                background-color: white;
                border-radius: 8px;
                border: 0.5px solid #dddddd;
                font-size: 16px;
                &.active{background-color: rgba(180, 250, 152, .7);}
            }
        }
        .articleListBox{
            background-color: #fafafa;
            .articleCard{
                border: 1px solid #ddd;
                border-radius: 8px;

                h3{
                    margin: 0;
                    padding: 8px 0 4px;
                    border-bottom: 1px solid #eee;
                }
                >div{
                    width: 100%;
                }
            }
        }
    }



</style>