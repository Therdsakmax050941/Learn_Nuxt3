<template>
    <div class="container_content">
        <h1>About</h1>
        <img src="/image/about.svg" alt="shopping" />
    </div>
</template>

<script setup>
useHead({
    title: 'MyShop | เกี่ยวกับเรา',
    meta: [{name: 'description',content: 'ซื้อขายผ่านระบบต่างๆ,ขายของออนไลน์,ซื้อของออนไลน์',}]
})
</script>

<style  scoped>
  .container_content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
img{
    width: 700px;
    height: 600px;
}
</style>