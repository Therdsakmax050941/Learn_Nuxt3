<template>
  <div>
    <header as="nav" class="bg-gray-800">
      <nav class="navbar navbar-dark border-bottom">
        <div class="flex h-16 items-center justify-between">
          <div class="flex items-center"> <!-- เพิ่ม class flex items-center -->
            <div class="navbar-brand" style="margin-right: 20px;">
              <img src="/image/logo.svg" alt="shopping" />
            </div>
            <div class="flex space-x-4 text-white">
              <NuxtLink to="/" class="nav-link">หน้าแรก</NuxtLink>
              <NuxtLink to="/about" class="nav-link">เกี่ยวกับเรา</NuxtLink>
              <NuxtLink to="/products" class="nav-link">สินค้าทั้งหมด</NuxtLink>
            </div>
          </div>
        </div>
      </nav>
    </header>
  </div>
  <div class="content">
    <slot />
  </div>
</template>

<script setup>
import 'bootstrap/dist/css/bootstrap.css'
</script>

<style scoped>
.navbar-brand label {
  color: rgb(0, 0, 0);
  font-size: 50px;
  font-weight: bold;
}

.navbar {
  margin-bottom: 20px;
  font-weight: bold;
}

.navbar-brand {
  margin-right: 0;
}

.flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-link {
  margin-left: 12px;
  font-size: 22px;
}

.nav-link:hover {
  color: orange;
}
</style>
