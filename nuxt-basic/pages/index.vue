<template>
  <div class="container">
    <div class="input-group">
      <div class="form-outline">
        <input type="search" v-model="inputSearch" @input="fetchData" class="form-control" />
        <label class="form-label" for="form1">Search</label>
      </div>
    </div>
    <div class="">
      <div v-for="product in products" :key="product.id" class="product-card">
        <div class="card  mt-5 col-4">
          <img :src="product.thumbnail" class="card-img-top" :alt="product.title" />
          <div class="card-body">
            <h5 class="card-title">{{ product.title }}</h5>
            <p class="card-text">{{ product.description }}</p>
            <p class="card-text">Price: {{ product.price }} $</p>
            <NuxtLink :to="'/products/' + product.id" class="btn btn-primary">Details</NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import 'bootstrap/dist/css/bootstrap.css';

const inputSearch = ref('');
const products = ref([]); // Assuming products will be an array
const total = ref(0);

const fetchData = async () => {
  try {
    const response = await fetch(`https://dummyjson.com/products/search?q=${inputSearch.value}`);
    const data = await response.json();
    products.value = data.products; // Update products with the fetched data array
    total.value = data.total; // Assign the total count
  } catch (error) {
    console.error(error);
  }
};

useHead({
  title: 'MyShop | หน้าแรก',
  meta: [{ name: 'description', content: 'ซื้อขายผ่านระบบต่างๆ,ขายของออนไลน์,ซื้อของออนไลน์' }]
});
</script>


  

<style scoped>
.product-card {
  display: flex;
  justify-content: space-between;
  gap: 20px;
}

.product-card .card {
  width: 300px;
}
.container_content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

img {
  width: 700px;
  height: 600px;
}
</style>