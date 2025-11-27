<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

const products = ref([])

// 表單資料
const newId = ref('')
const newName = ref('')
const newPrice = ref('')

// POST 新增產品
const addProduct = async () => {
  try {
    const newProduct = {
      name: newName.value,
      price: parseFloat(newPrice.value),
    }
    const res = await axios.post('http://localhost:5161/products', newProduct)
    products.value.push(res.data)

    // 清空表單
    newName.value = ''
    newPrice.value = ''
  } catch (error) {
    alert('抓取資料失敗，請稍後再試')
    console.error(error)
  }
}
</script>

<template>
  <div>
    <h2>新增產品</h2>
    <form class="選單" @submit.prevent="addProduct">
      <label for="name">name</label>
      <input id="name" v-model="newName" type="text" />

      <label for="price">Price</label>
      <input id="price" v-model="newPrice" type="number" step="0.01" />

      <button type="submit">新增產品</button>
    </form>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  padding-left: 10%;
  padding-right: 10%;
}

.選單 {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
</style>
