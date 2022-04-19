<template>
  <div class="box">
    <div class="paper container container-sm">
      <h3>用户登录</h3>
      <div class="row">
        <div class="sm-4 col" for="name">账号</div>
        <input class="sm-4 col border border-6 border-primary" placeholder="请输入账号..." type="text" name="name" v-model="user.username" id="paperInputs1" />
      </div>
      <div class="row">
        <label class="sm-4 col" for="password">密码</label>
        <input class="sm-4 col border border-6 border-primary" placeholder="请输入密码..." type="password" name="password" v-model="user.password" id="paperInputs1">
      </div>
      <p class="row flex-spaces">
        <button style="width: 150px;" @click="signRow">登录</button>
        <button style="width: 150px;" popover-top="点击注册后登录" @click="registerRow">注册</button>
      </p>
    </div>
  </div>
</template>
<script>
import { reactive } from "vue";
import { useRouter } from "vue-router";
export default ({
  setup () {
    const router = useRouter();
    let user = reactive({
      username: "",
      password: "",
    });
    function signRow () {
      router.push({ path: '/home' })
    }
    function registerRow () {
      router.push({ path: '/home' })
    }
    return {
      user,
      signRow,
      registerRow
    };
  },
})
</script>

<style  scoped>
.box {
  text-align: center;
}
.container {
  margin-top: 10%;
}
</style>
