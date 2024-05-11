<template>
  <div class="d-flex justify-content-center">
    <div class="card w-75 p-2 mt-5  ">
      <div class="card-container">
        <div v-for="car in cars" :key="car.id" class="card">
          <div class="card-image">
            <img :src="car.image" alt="product-image">
          </div>
          <div class="card-body">
            <nuxt-link :to="`/product/${car.id}`">
              <h2 class="title">{{ car.make }} {{ car.model }} {{ car.year }}</h2>
            </nuxt-link>
            <p class="price">{{ car.price }} USD</p>
            <!-- Add more details if needed -->
          </div>
        </div>
      </div>
    </div>
  </div>


</template>

<script setup>
const { data: products } = await useFetch('https://663dc985e1913c476795689a.mockapi.io/PertiiezApi/Car')
const { data: cars } = await useFetch('https://freetestapi.com/api/v1/cars ')

console.log(products)
</script>



<style scoped>
h2.title{
  text-decoration: none;
  color: black;
  font-size: 1rem;
  
}
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  width: 200px;
  margin: 10px;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
}

.card:hover {
  transform: translateY(-5px);
}

.card-image {
  position: relative;
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: auto;
  transition: transform 0.3s ease-in-out;
}

.card:hover .card-image img {
  transform: scale(1.05);
}

.card-content {
  padding: 20px;
  background-color: #fff;
}

.card-content h2 {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

.card-content .price {
  font-size: 1.25rem;
  color: #2ecc71;
  /* Green color for price */
}
</style>
