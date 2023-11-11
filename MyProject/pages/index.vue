<template>
  <div class="container mt-5">
    <h1 class="text-center my-4">ให้เราช่วยคุณค้นหาสินค้าที่คุณต้องการ</h1>
    <div class="input-group mb-3">
      <input
        type="search"
        v-model="inputSearch"
        class="form-control"
        placeholder="Search for products"
        aria-label="Search"
        aria-describedby="searchButton" 
      />
      <button class="btn btn-outline-secondary" type="button" @click="fetchData" id="searchButton">
        <img src="/icons/search.svg" />
      </button>
    </div>
    <div class="row row-cols-1 row-cols-md-4 g-4">
      <div v-for="product in products" :key="product.id" class="col">
        <div class="card h-100">
          <img :src="product.thumbnail" class="card-img-top" :alt="product.title" height="250" />
          <div class="card-body d-flex flex-column">
            <h5 class="card-title">{{ product.title }}</h5>
            <p v-if="!product.showFullDescription" class="card-text flex-grow-1">{{ truncateDescription(product.description) }}</p>
            <p v-else class="card-text flex-grow-1">{{ product.description }}</p>
            <div v-if="product.description.length > 100">
              <button @click="showFullDescription(product)" v-if="!product.showFullDescription" class="btn btn-secondary">Show More</button>
            </div>
            <p class="card-text btn btn-dark mt-3">Price: {{ product.price }} $</p>
            <NuxtLink :to="'/products/' + product.id" class="btn border">Details</NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const inputSearch = ref('');
const products = ref([]);
const total = ref(0);

const fetchData = async () => {
  try {
    const response = await fetch(`https://dummyjson.com/products/search?q=${inputSearch.value}`);
    const data = await response.json();
    products.value = data.products.map(product => ({
      ...product,
      showFullDescription: false
    }));
    total.value = data.total;
  } catch (error) {
    console.error(error);
  }
};

const showFullDescription = (product) => {
  product.showFullDescription = true;
};

const truncateDescription = (description) => {
  if (description.length > 100) {
    return description.substring(0, 100) + '...';
  }
  return description;
};

useHead({
  title: 'MyShop | หน้าแรก',
  meta: [{ name: 'description', content: 'ซื้อขายผ่านระบบต่างๆ,ขายของออนไลน์,ซื้อของออนไลน์' }]
});
</script>

<style scoped>
/* Customize styling as needed */
</style>
