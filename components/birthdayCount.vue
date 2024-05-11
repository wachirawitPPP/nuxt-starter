<template>
    <div>
       
      <vue-countdown :time="time" v-slot="{ days, hours, minutes, seconds }">
        <p v-if="days > 0">Birthday Countdown: {{ days }} days, {{ hours }} hours, {{ minutes }} minutes, {{ seconds }} seconds</p>
        <p v-else>Happy Birthday!</p>
      </vue-countdown>
    </div>
  </template>
  
  <script>
  import VueCountdown from 'vue-countdown';
  
  export default {
    components: {
      VueCountdown
    },
    props: {
      birthday: {
        type: String,
        required: true
      }
    },
    computed: {
      time() {
        const birthdayDate = new Date(this.birthday);
        const now = new Date();

        return (birthdayDate - now);
      }
    }
  };
  </script>
  