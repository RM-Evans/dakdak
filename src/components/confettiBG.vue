<script setup>
import { ref, watch, onUnmounted } from 'vue'
import JSConfetti from 'js-confetti'



const props = defineProps({
  catClicked: Boolean
})

let jsConfetti = null
let intervalId = null




function startConfetti() {
  if (!jsConfetti) jsConfetti = new JSConfetti()
  if (intervalId) return // already running, do nothing

  jsConfetti.addConfetti()

  intervalId = setInterval(() => {
    jsConfetti.addConfetti()
  }, 4000)
}

function stopConfetti() {
  if (intervalId) {
    clearInterval(intervalId)
    intervalId = null
  }
}


watch(() => props.catClicked, (newVal) => {
  if (newVal) {
    if (!jsConfetti ) jsConfetti = new JSConfetti()
    startConfetti()
  } else {
    stopConfetti()
  }
})


onUnmounted(() => {
  stopConfetti()
})

</script>
