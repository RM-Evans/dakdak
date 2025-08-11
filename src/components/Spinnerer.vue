<script setup>
import { ref } from 'vue';
</script>
<template>
  <div class="spinner">
    <img src="../assets/pearlVec.png" alt="Loading..." class="pearlImg" />
  </div>
  </template>
<style scoped>
.pearlImg {
  width: 300px;
  height:300px;
}
.spinner {
  width: 100px;
  height: 100px;
  display: flex;
      justify-content: center;
      align-items: center;
  border-radius: 50%;
  animation: rotate 2s linear infinite; /* Apply the animation */
}
@keyframes rotate {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>