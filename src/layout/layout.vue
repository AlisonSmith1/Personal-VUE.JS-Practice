<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from '../../src/components/HelloWorld.vue'
</script>

<template>
  <div class="header">
    <img alt="Vue logo" class="logo" width="50" height="50" />
    <div class="info">
      <HelloWorld msg="You did it!" />
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/add">Add</RouterLink>
        <RouterLink to="/edit">Edit</RouterLink>
      </nav>
    </div>
  </div>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center; /* 垂直置中 */
  gap: 20px; /* logo 與文字區間距 */

  padding-left: 10%;
  padding-right: 10%;
}

.info {
  display: flex;
  flex-direction: column; /* 文字 + nav 垂直排列 */
}

nav {
  display: flex;
  gap: 20px;
  margin-top: 5px;
}
</style>
