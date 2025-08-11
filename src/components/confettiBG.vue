<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import JSConfetti from 'js-confetti'

const colors = ['#ff6b6b', '#6bc1ff', '#6bff95', '#ffd86b']
const currentColorIndex = ref(0)

let intervalId = null
let jsConfetti = null

function changeBackgroundColor() {
  document.body.style.backgroundColor = colors[currentColorIndex.value]
}

onMounted(() => {
  jsConfetti = new JSConfetti()

  changeBackgroundColor()
  jsConfetti.addConfetti()

  intervalId = setInterval(() => {
    currentColorIndex.value = (currentColorIndex.value + 1) % colors.length
    changeBackgroundColor()
    jsConfetti.addConfetti()
  }, 4000)
})

onBeforeUnmount(() => {
  clearInterval(intervalId)
  document.body.style.backgroundColor = ''
})
</script>

