<template>
  <div class="test">用户名:{{ mainStore.name }}<br />长度:{{ mainStore.nameLength }}</div>
  <hr />
  <button @click="updateName">修改store中的name</button>
  <hr />
  <el-button type="primary" @click="intoLogin">Primary</el-button>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';
import { useMainStore } from '@/store/main'

const mainStore = useMainStore()
const router = useRouter()

const updateName = () => {
  mainStore.$patch({
    name: '名称被修改了,nameLength也随之改变了',
  })
}

const intoLogin = () => {
  router.push("/home")
}
</script>

<style lang="scss" scoped>
.test {
  color: $test-color;
}
</style>
