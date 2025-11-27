<script setup>
import { RouterLink, RouterView } from 'vue-router'
import layout from './layout/layout.vue'
</script>

<template>
  <div class="main">
    <section class="layout">
      <layout />
    </section>

    <section class="content">
      <RouterView />
    </section>
    <div class="float-window"><a href="https://www.msn.com/zh-tw">Edge</a></div>
  </div>
</template>

<style>
.main {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.layout {
  border: 2px solid red;
}

.content {
  flex: 1;
  overflow-y: auto;
  border: 2px solid red; /* 2px 寬、實線、黑色 */
}

body {
  color: #ffffff;
  background-color: #222222;
}

.float-window {
  position: fixed;
  bottom: 20px; /* 距離底部 20px */
  right: 20px; /* 距離右側 20px */
  background: white;
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.15);
}
</style>
