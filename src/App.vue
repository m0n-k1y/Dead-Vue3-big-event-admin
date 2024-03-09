<script setup>
import { useRouter, useRoute } from 'vue-router'
import { useUserStore, useCounterStore } from '@/stores'
const router = useRouter()
const route = useRoute()

const counterStore = useCounterStore()
const userStore = useUserStore()

const goList = () => {
  router.push('/list')
  console.log(router, route)
}
</script>

<template>
  <div>
    <router-view></router-view>
    <hr />
    我是APP
    <Test-demo></Test-demo>

    <el-button @click="$router.push('/home')">跳首页</el-button>
    <el-button @click="goList">跳列表页</el-button>
    <el-button type="primary" plain>Primary</el-button>
    <el-button type="success" plain>Success</el-button>
    <p>{{ userStore.token }}</p>
    <el-button @click="userStore.setToken('dskfjskdfjsdkfj')">登录</el-button>
    <el-button @click="userStore.removeToken()">退出</el-button>
    <hr />
    {{ counterStore.count }}
    <el-button @click="counterStore.add(2)">加法</el-button>
  </div>
</template>

<style scoped></style>
@/stores/modules/user
