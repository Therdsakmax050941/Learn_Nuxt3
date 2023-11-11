<template>
  <h1 class="text-center my-4">
      รายละเอียด
    </h1>
  <div class="border shadow p-3 rounded container">
  <div class="container">
      <div class="row row-cols-1 row-cols-md-4 g-4 mt-4">
        <div v-for="product in data.products" :key="product.id" class="col">
          <div class="card h-100">
            <img class="card-img-top border border-top-0" :src="product.thumbnail" alt="Card image cap" height="250">
            <div class="card-body d-flex flex-column">
              <h5 class="card-title">{{ product.title }}</h5>
              <p class="card-text flex-grow-1">{{ product.description }}</p>
              <div class="d-flex justify-content-between">
                <NuxtLink :to="`/products/${product.id}`" class="card-text btn border">รายละเอียด</NuxtLink>
                <span class="card-text btn btn-dark">ซื้อ {{ product.price }} $</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
<script setup>
useHead({
  title: 'MyShop | สินค้าทั้งหมด',
  meta: [{ name: 'description', content: 'ซื้อขายผ่านระบบต่างๆ,ขายของออนไลน์,ซื้อของออนไลน์' }],
})
const { data: data } = await useFetch('https://dummyjson.com/products')
</script>
  
<style scoped></style>
  