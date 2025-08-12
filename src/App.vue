<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Spinnerer from './components/Spinnerer.vue';
import SoundPlayer from './components/SoundPlayer.vue';
import Background from './components/Background.vue';
import { ref } from 'vue';

import stayHouse from './assets/stayHouse.mp3';
import ConfettiBG from './components/confettiBG.vue';


const player = ref(null);
const isPlaying = ref(false);
const catClicked = ref(false)

function togglePlay() {
  if (isPlaying.value) {
    player.value.pause();
      catClicked.value = false;
  } else {
    player.value.play();
   catClicked.value = true;
  }
  
  isPlaying.value = !isPlaying.value;
  // console.log('Toggle play:', isPlaying.value);

}

</script>

<template>
<HelloWorld :catClicked="catClicked" msg="Click on Pearl"/>
  <Spinnerer :catClicked="catClicked" @click="togglePlay"/>
  <SoundPlayer ref="player" :src="stayHouse"/>
  <ConfettiBG :catClicked="catClicked"/>
  <Background :catClicked="catClicked"/>


</template>
// duplicating



