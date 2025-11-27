<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

const products = ref([])

// 表單資料
const newId = ref('')
const newName = ref('')
const newPrice = ref('')

// GET 產品列表
const getProducts = async () => {
  try {
    const res = await axios.get('http://localhost:5161/products')
    products.value = res.data
  } catch (error) {
    console.error(error)
  }
}

// 頁面載入時自動抓資料
onMounted(() => {
  getProducts()
})
</script>

<template>
  <div>
    <h2>產品列表</h2>
    <ul>
      <li v-for="p in products" :key="p.id">{{ p.name }} : ${{ p.price }}</li>
    </ul>
  </div>
</template>

<style scoped>
div {
  position: relative;
  left: 10%;
}
</style>
