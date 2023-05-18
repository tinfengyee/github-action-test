<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)
const state = ref()
const fetchApi = () => {
  fetch('https://bible-api.com/john 3:16')
    .then(res => {
      return res.json()
    })
    .then(res => {
      console.log(res)
      state.value = res
    })
}
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <button type="button" @click="fetchApi">Fetch</button>
    <p>{{ JSON.stringify(state) }}</p>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
  <p>你好鸭</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
