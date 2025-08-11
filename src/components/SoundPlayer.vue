<template>
    <audio ref="audio" :src="src"></audio>
  </template>
  
  <script>
  export default {
    name: 'SoundPlayer',
    props: {
      src: { type: String, required: true }
    },
    methods: {
      play() {
        this.$refs.audio.play();
      },
      pause() {
        this.$refs.audio.pause();
      }
    }
  };
  </script>