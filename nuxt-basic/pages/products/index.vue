<template>
    <div class="justify-center my-8">
      <h1 class="text-center mr-4">
        รายละเอียด
      </h1>
      <div class="mx-5 ">
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 lg:grid-cols-4 gap-4">
          <div v-for="product in data.products" :key="product.id" class="my-8">
            <div class="card max-w-xl">
              <img class="card-img-top" :src="product.thumbnail" alt="Card image cap">
              <div class="card-body">
                <h5 class="card-title">{{ product.title }}</h5>
                <p class="card-text">{{ product.description }}</p>
                <div class="flex space-x-2">
                  <NuxtLink :to="`/products/${product.id}`" class="btn btn-primary">รายละเอียด</NuxtLink>
                  <span class="btn btn-success">Buy {{ product.price }} $</span>
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
    meta: [{ name: 'description', content: 'ซื้อขายผ่านระบบต่างๆ,ขายของออนไลน์,ซื้อของออนไลน์' }]
  })
  const { data: data } = await useFetch('https://dummyjson.com/products?limit=10')
  </script>
  
  <style scoped>
  .container_content {
    margin-top: 3rem;
    margin-left: 1rem;
  }
  .card-img-top {
    max-width: 100%;
    height: 300px; /* ปรับตามที่ต้องการ */
  }
  </style>
  