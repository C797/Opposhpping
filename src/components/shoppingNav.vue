<template>
    <div class="oppo-nav">
        <div class="contentCenter">
            <div class="oppoLeft">
                <img src="https://dsfs.oppo.com/oppo/shop-pc-v2/main/img/9c6f387.png">
            </div>
            <div class="oppoRight">
                <div class="oppoItem">新机专区</div>
                <div class="oppoItem">经典专区</div>
                <div class="oppoItem">智能配件</div>
                <div class="oppoItem">智能家居</div>
            </div>
        </div>
    </div>
</template>

<script lang='ts'>
import { reactive,toRefs,onBeforeMount,onMounted} from 'vue'
interface DataProps {}
export default {
    name: '',
    setup() {
        const data: DataProps = reactive({
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
<style lang='less' scoped>
.oppo-nav{
    height: 84px;
    background: #fff;
    border-bottom: 1px solid #e5e5e5;
    .contentCenter{
        height: 84px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        .oppoLeft{
            font-size: 30px;
            color: #222;
            cursor: pointer;
            img{
                width: 240px;
            }
        }
        .oppoRight{
            display: flex;
            height: 84px;
            align-items: center;
            font-size: 14px;
            .oppoItem{
                margin-left: 16px;
                cursor: pointer;
                color: #888;
                &:hover{
                    color: #222;
                }
            }
        }
    }
}
</style>