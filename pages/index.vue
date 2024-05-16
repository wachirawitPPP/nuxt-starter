<template>
  <div class="d-flex flex-column align-items-center">
    <img class="pic m-3" src="/public/mochi-cat-love.gif" alt="">
    <h3 v-if="timeRemainingState" class="time-anv">Its our Aniversary 2 Years.💕💕💕💕💖💖💖💖</h3>
    <h6 class="mt-4" v-if="!timeRemainingState">There are</h6>
    <h6 class="time m-4">{{ timeRemaining }}</h6>
    <div class="col d-flex align-items-center">
      <h6 v-if="!timeRemainingState">until our anniversary, darling.</h6>
    </div>
    <nuxt-link to="/journey">
      <div v-if="timeRemainingState">
        <button class="btn p-3 m-4"><h5>I have something to tell you. 💌</h5></button>
      </div>
    </nuxt-link>
    <img class="run" src="/public/quby-run.gif" alt="">
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

// Set the anniversary date
const anniversaryDate = new Date('2024-05-17 21:56:40');

// Calculate time remaining
const timeRemaining = ref('');
const timeRemainingState = ref(false);

const calculateTimeRemaining = () => {
  const now = new Date();
  const difference = anniversaryDate.getTime() - now.getTime();

  if (difference > 0) {
    const days = Math.floor(difference / (1000 * 60 * 60 * 24));
    const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((difference % (1000 * 60)) / 1000);

    timeRemaining.value = `${days} days, ${hours} hours, ${minutes} minutes, ${seconds} seconds`;
  } else {
    timeRemaining.value = 'Its our Aniversary 2 Years.💕💕💕💕💖💖💖💖';
    timeRemainingState.value = true;
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

.run {
  width: 10%;
  height: 10%;
}

.time {
  color: pink;
}

.time:hover {
  color: black;
}

.page-enter-active,
.page-leave-active {
  transition: opacity 0.5s;
}
.page-enter,
.page-leave-to {
  opacity: 0;
}

.btn {
  background-color: #E1AFD1;
}
.time-anv{
  color: #E1AFD1;
  margin-top: 50px;
}

/* Responsive Styles */
@media (max-width: 1200px) {
  .pic {
    width: 40%;
  }
  .btn {
    padding: 2rem;
  }
  h6.time {
    font-size: 1.5rem;
  }
}

@media (max-width: 992px) {
  .pic {
    width: 50%;
  }
  .run {
    width: 15%;
  }
  .btn {
    padding: 1.5rem;
  }
  h6.time {
    font-size: 1.25rem;
  }
}

@media (max-width: 768px) {
  .pic {
    width: 60%;
  }
  .run {
    width: 20%;
  }
  .btn {
    padding: 1.2rem;
  }
  h6.time {
    font-size: 1rem;
  }
}

@media (max-width: 576px) {
  .pic {
    width: 70%;
  }
  .run {
    width: 25%;
  }
  .btn {
    padding: 1rem;
  }
  h6.time {
    font-size: 0.85rem;
  }
}
</style>
