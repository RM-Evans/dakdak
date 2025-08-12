<script setup>

import { ref } from 'vue';

const props = defineProps({
  catClicked: Boolean
})
</script>
<template>
  <div class="spinner" :class="{ spinning: catClicked }">
    <img src="../assets/pearlVec.png" alt="Loading..." class="pearlImg" />
  </div>
  </template>
<style scoped>
.pearlImg {
  width: 300px;
  height:300px;
}
.spinner {
  position: fixed;
  top: 40%;
right: 50%;
  left: 50%;

  display: flex;
      justify-content: center;
      align-items: center;
}
.spinning {
  animation: rotate 2s linear infinite;
 
}
@keyframes rotate {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>