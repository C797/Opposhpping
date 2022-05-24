<template>
    <div class="fiexdTop">
        <loginNav></loginNav>
        <shoppingNav></shoppingNav>
    </div>
    <div class="main">
        <Banner></Banner>
        <div class="commodity contentCenter">
            <div class="commodity-item" v-for="(item,index) in commodityList" :key="index">
                <img :src="item.cover">
            </div>
        </div>
        <div class="contentCenter commodity-end">
            <div class="commodity-endBig"><img :src="commodityEndData.bigData.cover"></div>
            <div class="commodity-endMin" v-for="(item,index) in commodityEndData.minData" :key="index">
                <div class="endMin-cover">
                    <img :src="item.cover">
                </div>
                <div class="endMin-title">{{item.title}}</div>
                <div class="endMin-price">￥{{item.price}}</div>
            </div>
        </div>
    </div>
</template>

<script lang='ts'>
import { reactive,toRefs,onBeforeMount,onMounted} from 'vue'
import loginNav from '../../components/loginNav.vue'
import shoppingNav from '../../components/shoppingNav.vue'
import Banner from '../../components/Banner.vue'
interface DataProps {}
export default {
    name: 'index',
    setup() {
        const data: DataProps = reactive({
            commodityList:[
                {id:1,title:'OPPO Reno7',colorList:"红丝绒,星雨心愿,星夜黑,晨曦金",price:2599,describe:'人像视频大师|6400万超清主摄',cover:'https://dsfs.oppo.com/archives/202203/202203100403056229bcad6b967.png'},
                {id:2,title:'OPPO K9x',colorList:"黑曜武士,银紫超梦",price:1349,describe:'6400万超清三摄|5000mAh',cover:'https://dsfs.oppo.com/archives/202203/20220309100322622815761652e.png'},
                {id:3,title:'OPPO Pad首款平板',colorList:"",price:2299,describe:'骁龙™870处理器|自由星空设计',cover:'https://dsfs.oppo.com/archives/202203/2022030912032162277ec1b6e98.png'},
                {id:4,title:'OPPO EncoX2',colorList:"",price:899,describe:'限时立减100元|独家12期免息',cover:'https://dsfs.oppo.com/archives/202203/202203081203266226d912c8c68.png'}
            ],
            commodityEndData:{
                bigData:{id:10,title:'Find X5 Pro',cover:'https://dsfs.oppo.com/archives/202203/20220303100321622021715fab2.png'},
                minData:[
                    {id:11,title:'Find X5 Pro 白瓷',price:6299,cover:'https://dsfs.oppo.com/omp/1646102912064-_-17d2e5ab3ab549cbb0c6b891b9e91bb0.png'},
                    {id:12,title:'Find X5 Pro 天玑版',price:5799,cover:'https://dsfs.oppo.com/omp/1646102926133-_-f4fc4fd7a88941f38f4fad1ad093f3ee.png'},
                    {id:13,title:'Find X5 Pro 天玑版',price:5799,cover:'https://dsfs.oppo.com/omp/1646102942242-_-d6a9085c248e4a8b8ed0d794440ff35b.png'}
                ]
            }
        })
        onBeforeMount(() => {
            console.log('2.组件挂载页面之前执行----onBeforeMount')
        })
        onMounted(() => {
            console.log('3.-组件挂载到页面之后执行-------onMounted')
        })
        const refData = toRefs(data);
        return {
            ...refData,
        }
    },
    components:{
        loginNav,
        shoppingNav,
        Banner
    }
  };
</script>
<style lang='less' scoped>
.fiexdTop{
    width: 100%;
    position: fixed;
    top: 0;left: 0;
    z-index: 999;
}
.main{
    padding-top: 150px;
    .commodity{
        margin-top: 30px;
        margin-bottom: 30px;
        column-count: 2;
		column-gap: 20px;
        .commodity-item{
            background: #fff;
            margin-bottom: 20px;
            cursor: pointer;
            
            img{
                width: 100%;
                box-shadow:none;
                transition:all 1s;
                -moz-transition:all 1s; /* Firefox 4 */
                -webkit-transition:all 1s; /* Safari and Chrome */
                -o-transition:all 1s; /* Opera */
                &:hover{
                    box-shadow:0 20px 60px rgba(0, 0, 0, 0.1);
                }
            }
        }
    }
    .commodity-end{
        display: flex;
        padding-bottom: 50px;
        .commodity-endBig{
            width: 488px;
            height: 300px;
            cursor: pointer;
            img{
                width: 100%;
                height: 100%;
            }
        }
        .commodity-endMin{
            flex: 1;
            background: #fff;
            margin-left: 15px;
            height: 300px;
            border-radius: 12px;
            cursor: pointer;
            box-shadow:none;
            transition:all 1s;
            -moz-transition:all 1s; /* Firefox 4 */
            -webkit-transition:all 1s; /* Safari and Chrome */
            -o-transition:all 1s; /* Opera */
            &:hover{
                box-shadow:0 20px 60px rgba(0, 0, 0, 0.1);
            }
            .endMin-cover{
                width: 100%;
                height: 160px;
                display: flex;
                justify-content: center;
                align-items: center;
                img{
                    width: 130px;
                    height: 120px;
                }
            }
            .endMin-title{
                font-size: 15px;
                color: #222;
            }
            .endMin-price{
                font-size: 18px;
                color: #f34141;
                margin-top: 40px;
            }
        }
    }
}
</style>