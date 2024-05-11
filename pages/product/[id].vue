<template>
    <div class="container-fluid vh-100 mt-5">
      <div class="card">
        <div class="card-header">
          <h3>Details</h3>
        </div>
        <div class="card-body">
          <div v-if="cars">
            <h5 class="card-title">{{ cars.make }} {{ cars.model }}</h5>
            <p class="card-text">Year: {{ cars.year }}</p>
            <p class="card-text">Color: {{ cars.color }}</p>
            <p class="card-text">Price: ${{ cars.price }}</p>
            <!-- Add more details here as needed -->
          </div>
          <div v-else>
            <p>Loading...</p>
          </div>
        </div>
      </div>
    </div>
  </template>

<script setup>
    const {id} = useRoute().params
    const { data: cars } = await useFetch(`https://freetestapi.com/api/v1/cars/${id}`)
    console.log(cars)
</script>

<style scoped>
.card {
  width: 100%; /* Adjust the width as needed */
  max-width: 100%; /* Limit the maximum width if desired */
}
.card-header{
    background-color: #ffda03;
}
</style>