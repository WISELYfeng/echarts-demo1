<template>
  <h1 class="test">一个测试1111</h1>
  <div>{{ mainStore.name }} : {{ mainStore.nameLength }}</div>
  <hr />
  <button @click="updateName">修改name</button>
  <el-button type="primary">蓝色</el-button>
</template>

<script setup lang="ts">
import { useMainStore } from '@/store/main'
const mainStore = useMainStore()
const updateName = () => {
  mainStore.$patch({
    name: '超级管理员修改',
  })
}
</script>

<style lang="scss" scoped>
.test {
  color: $test-color;
}
</style>
