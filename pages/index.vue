<template>
  <div class="d-flex flex-column align-items-center">
    <img class="pic" src="/public/mochi-cat-love.gif" alt="">
    <h6 class="mt-4">There are</h6>
    <h6 class="time">{{ timeRemaining }}</h6>
    <div class="col d-flex  align-items-center">
      <h6 class="">until our anniversary, darling.</h6 >
        
    </div>
    <img class="run" src="/public/quby-run.gif" alt="">
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

// Set the anniversary date
const anniversaryDate = new Date('2024-05-17 00:00:00');

// Calculate time remaining
const timeRemaining = ref('');

const calculateTimeRemaining = () => {
  const now = new Date();
  const difference = anniversaryDate.getTime() - now.getTime();

  if (difference > 0) {
    const days = Math.floor(difference / (1000 * 60 * 60 * 24));
    const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((difference % (1000 * 60)) / 1000);

    timeRemaining.value = `${days} days, ${hours-7} hours, ${minutes} minutes, ${seconds} seconds`;
  } else {
    timeRemaining.value = 'Anniversary has passed!';
  }
};

// Update the countdown every second (only in the browser)
if (process.client) {
  const interval = setInterval(calculateTimeRemaining, 1000);

  // Stop the interval when the component is unmounted
  onUnmounted(() => clearInterval(interval));
}

// Calculate time remaining on component mount
onMounted(calculateTimeRemaining);
</script>

<style scoped>
.pic {
  width: 30%;
}
.run{
  width: 10% ;
  height: 10%;
}
.time{
  color: pink;
}
.time:hover{
  color: black;
}
</style>
