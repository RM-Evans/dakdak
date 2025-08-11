<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Spinnerer from './components/Spinnerer.vue';
import SoundPlayer from './components/SoundPlayer.vue';
import Background from './components/Background.vue';
import confettiBG from './components/confettiBG.vue';
import { ref } from 'vue';

import stayHouse from './assets/stayHouse.mp3';
import ConfettiBG from './components/confettiBG.vue';


const player = ref(null);
const isPlaying = ref(false);

function togglePlay() {
  if (isPlaying.value) {
    player.value.pause();
  } else {
    player.value.play();
  }
  isPlaying.value = !isPlaying.value;
  console.log('Toggle play:', isPlaying.value);
}

</script>

<template>

  <!-- <HelloWorld msg="Vite + Vue" /> -->
  <Spinnerer @click="togglePlay"/>
  <SoundPlayer ref="player" :src="stayHouse"/>
  <ConfettiBG />
   <Background/>


</template>



<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

</style>
