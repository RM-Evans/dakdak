<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const colors = ['#FFF55E', '#35E871', '#34C2AA', '#671596']
const currentColorIndex = ref(0)
const bgColor = ref(colors[currentColorIndex.value])

let intervalId = null
function changeBackgroundColor() {
  document.body.style.backgroundColor = colors[currentColorIndex.value]
}

onMounted(() => {
  intervalId = setInterval(() => {
    currentColorIndex.value = (currentColorIndex.value + 1) % colors.length
     changeBackgroundColor()
  }, 2000)
})

onBeforeUnmount(() => {
  clearInterval(intervalId)
})
</script>



