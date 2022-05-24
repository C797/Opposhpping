<template>
    <div class="contentCenter">
        <el-carousel indicator-position="bottom" :interval="5000">
            <el-carousel-item v-for="item in banners" :key="item">
                <img :src="item.url">
            </el-carousel-item>
        </el-carousel>
    </div>
</template>

<script lang='ts'>
import { reactive,toRefs,onBeforeMount,onMounted} from 'vue'
interface DataProps {}
export default {
    name: '',
    setup() {
        const data: DataProps = reactive({
            banners:[
                {id:1,url:'https://dsfs.oppo.com/archives/202203/202203081203316226da4338f29.png'}, 
                {id:2,url:'https://dsfs.oppo.com/archives/202203/202203051003326222c5e4d60cc.jpg'},
                {id:3,url:'https://dsfs.oppo.com/archives/202203/202203080203146226fa8af08a8.png'},
                {id:4,url:'https://dsfs.oppo.com/archives/202203/202203081203536226d9a5eee72.png'}
            ]
        })
        onBeforeMount(() => {
            
        })
        onMounted(() => {
            
        })
        const refData = toRefs(data);
        return {
            ...refData,
        }
    }
  };
</script>
<style scoped>
.el-carousel__item img{
  width: 100%;
}

div/deep/ .el-carousel__container{
    border-radius: 10px;
    height: 440px;
    overflow: hidden;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>