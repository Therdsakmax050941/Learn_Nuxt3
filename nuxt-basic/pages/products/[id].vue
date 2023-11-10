<template>
    <Head>
        <Title>MyShop | {{ product.title }}</Title>
        <Meta name="description" :content="product.description"  />
    </Head>
    <div class="container">
        <img :src="product.thumbnail" />
        <div class="detail mt-5">
            <h3> ชื่อ : {{ product.title }}</h3>
            <h3>ราคา : {{ product.price }} $</h3>
            <h3>ยี่ห้อสินค้า : {{ product.brand }}</h3>
            <p>รายละเอียด : {{ product.description }}</p>
        </div>
    </div>
</template>

<script setup>
const { id } = useRoute().params
const { data: product } = await useFetch('https://dummyjson.com/products/' + id)
console.log(product)

</script>

<style scoped></style>