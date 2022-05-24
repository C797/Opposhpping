<template>
  <div class="login-top">
      <div class="contentCenter">
          <div class="login-logo">
              OPPO官网
          </div>
          <div class="login-join">
              <span>登录</span>
              <span>注册</span>
              <span>购物车(0)</span>
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
<style lang="less" scoped>
.login-top{
    height: 36px;
    background: #222;
    color: #fff;
    font-size: 14px;
    .contentCenter{
        display: flex;
        justify-content: space-between;
        align-items: center;
        height:36px;
        .login-join{
            display: flex;
            align-items: center;
            span{
                display: block;
                height: 36px;
                padding: 0 20px;
                line-height: 36px;
                cursor: pointer;
                position: relative;
                &::after{
                    content: " ";
                    display: inline-block;
                    width: 1px;
                    height: 14px;
                    background: #fff;
                    line-height: 36px;
                    position: absolute;
                    top: 50%;right: 0;
                    transform: translateY(-50%);
                }
            }
        }
    }
}
</style>