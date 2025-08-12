<script setup>
import { ref } from 'vue'

const props = defineProps({
  msg: String,
  catClicked: Boolean
})

const count = ref(0)
</script>

<template>
<h1 :class="{ light: props.catClicked, dark: !props.catClicked }">
  click on pearl
</h1>
</template>

<style scoped>
.dark {
  color: #ffffff;
 
}
.light {
  /* color: #000000 !important; */
  visibility: hidden;
}
h1{

font-size: 30px;
margin-bottom: 150%;
  transition: color 0.3s ease;
}
</style>
const props = 