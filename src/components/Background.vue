<script setup>
import { ref, onMounted, onBeforeUnmount,watch } from 'vue'

const props = defineProps({
  catClicked: Boolean
})

const colors = ['#FFF55E', '#35E871', '#34C2AA', '#671596']
const currentColorIndex = ref(0)
// const bgColor = ref(colors[currentColorIndex.value])

let intervalId = null

function changeBackgroundColor() {
  document.body.style.backgroundColor = colors[currentColorIndex.value]
}

watch(
  () => props.catClicked,
  (active) => {
    clearInterval(intervalId)

    if (active) {
      // start cycling colors
      currentColorIndex.value = (currentColorIndex.value + 1) % colors.length
      changeBackgroundColor()
      intervalId = setInterval(() => {
        currentColorIndex.value = (currentColorIndex.value + 1) % colors.length
        changeBackgroundColor()
      }, 2000)
    } else {
      // reset to black immediately
      currentColorIndex.value = 0
      document.body.style.backgroundColor = '#000000'
    }
  },
  { immediate: true }
)

onBeforeUnmount(() => {
  clearInterval(intervalId)
})
</script>



