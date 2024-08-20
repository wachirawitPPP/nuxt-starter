<template>
  <div>
    <AppHeader />
    <NuxtPage />
  </div>
  <audio id="bg-music" ref="audioPlayer" loop>
    <!-- <source src="/public/landokmai.mp3" type="audio/mpeg"> -->
    Your browser does not support the audio element.
  </audio>
</template>

<script>
export default {
  mounted() {
    // Attach event listener to document body for touch or click
    document.body.addEventListener('click', this.handleInteraction, { once: true });
    document.body.addEventListener('touchstart', this.handleInteraction, { once: true });
  },
  methods: {
    handleInteraction() {
      // Play the audio when triggered by user interaction
      const audio = this.$refs.audioPlayer;
      audio.play().catch(error => {
        console.error("Audio playback failed: ", error);
      });
    }
  }
}
</script>

<style scoped>

</style>
