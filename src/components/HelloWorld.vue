<script setup>
import { ref } from 'vue'

const props = defineProps({
  msg: String,
  catClicked: Boolean
})

const count = ref(0)
</script>

<template>
  <div class="bapper">
 <h1 :class="{ cyberText: props.catClicked, hideCyberText: !props.catClicked }">
hang in there
 </h1>
  <h1 :class="{ light: props.catClicked, dark: !props.catClicked }">
    {{ props.msg }}
    </h1>

  </div>
</template>

<style scoped>
.dark {
  color: #ffffff;
  DROP-shadow: 0 10PX 20px rgba(33, 33, 33, 0.5);
 
}
.light {
  /* color: #000000 !important; */
  visibility: hidden;
}
h1{

font-size: 30px;

  transition: color 0.3s ease;
}
.cyberText {
color: #2ef038;
text-shadow: rgba(1, 29, 12, 0.3) 2px 2px 2px;
}
.hideCyberText {
  visibility: hidden;
}
.bapper {
  position: fixed;
  top: 20%;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
}
</style>
const props = 