<template>
  <div class="login_box">
      <h1>登录页</h1>
      <h2>{{name}}</h2>
      {{n}}
      <button @click="login">点击</button>
  </div>
</template>

<script>
import { reactive, toRefs } from "@vue/composition-api" // toRefs将数据变成响应式
export default {
    setup(props, {root}){
        const state = reactive({
            name: "于叔",
            n: 1
        })
        const login = () => {
            // return state.n++;
            root.$router.push("/home"); // vue3中没有this  root当做this用
        }
        return {
            ...toRefs(state),
            login
        }
    }
};
</script>

<style lang="scss" scoped>

</style>
