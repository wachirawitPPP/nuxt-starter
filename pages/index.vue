<template>
    <div class="container">
      <h2 class="text-center mt-5 mb-4">Happy Birthday, [Your Girlfriend's Name]!</h2>
      <img v-if="randomPosition&&!message" class="cry-cat" src="/public/crying-cat.gif" alt="">
      <div class="text-center">
        <button @click="showMessage" class="btn btn-lg btn-primary mr-3">Yes</button>
        <button v-if="showNoButton" @click="generateRandomButton" class="btn btn-lg btn-danger">No</button>
      </div>
      <button v-if="randomPosition&&!message" @click="handleRandomButtonClick" :style="{ top: randomPosition.top + 'px', left: randomPosition.left + 'px', position: 'absolute' }" class="btn btn-lg btn-warning">No!</button>
      
      <p v-if="message" class=" text-center mt-4">You said Yes! 🎉</p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const message = ref('');
  const randomPosition = ref(null);
  const showNoButton = ref(true);
  
  const showMessage = () => {
    message.value = 'You said Yes! 🎉';
    showNoButton.value = false;
  };
  
  const generateRandomButton = () => {
    const randomTop = Math.floor(Math.random() * window.innerHeight);
    const randomLeft = Math.floor(Math.random() * window.innerWidth);
    randomPosition.value = { top: randomTop, left: randomLeft };
    showNoButton.value = false;
  };
  
  const handleRandomButtonClick = () => {
    generateRandomButton();
  };
  </script>
  
  <style>
  
    
    .cry-cat{
    }
  </style>