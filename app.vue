<template>
  <div>
    <AppHeader />
    <NuxtPage />
  </div>
  <audio id="bg-music" ref="audioPlayer" controls loop>
    <source src="/public/landokmai.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>
</template>

<script>
export default {
  mounted() {
    // Attach event listener to document body for touch or click
    document.body.addEventListener('touchstart', this.handleInteraction);
    document.body.addEventListener('click', this.handleInteraction);
  },
  methods: {
    handleInteraction() {
      // Play the audio when triggered by user interaction
      const audio = this.$refs.audioPlayer;
      audio.play();
      
      // Remove the event listeners after the audio starts playing
      document.body.removeEventListener('touchstart', this.handleInteraction);
      document.body.removeEventListener('click', this.handleInteraction);
    }
  }
}
</script>

<style scoped>
#bg-music{
  display: none;
}
</style>
