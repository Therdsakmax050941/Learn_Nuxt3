<template>
  <div>
    <header>
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <NuxtLink to="/" class="nav-link">หน้าแรก</NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink to="/about" class="nav-link">เกี่ยวกับเรา</NuxtLink>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          สินค้า
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <NuxtLink to="/products" class="dropdown-item">สินค้าทั้งหมด</NuxtLink>
          <a class="dropdown-item" href="#">Another action</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
    </header>
    <div class="content">
      <slot />
    </div>
  </div>
</template>



  
<script setup>
useHead({
  link: [
    {
      rel: 'stylesheet',
      href: 'https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css',
      integrity: 'sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN',
      crossorigin: 'anonymous'
    },
    {
      rel: 'stylesheet',
      href: 'https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css',
      integrity: 'sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm',
      crossorigin: 'anonymous'
    }
  ],
  script: [
    {
      src: 'https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js',
      integrity: 'sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL',
      crossorigin: 'anonymous'
    },
    {
      src: 'https://code.jquery.com/jquery-3.2.1.slim.min.js',
      integrity: 'sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN',
      crossorigin: 'anonymous'
    },
    {
      src: 'https://cdn.jsdelivr.net/npm/popper.js@1.12.9/dist/umd/popper.min.js',
      integrity: 'sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q',
      crossorigin: 'anonymous'
    },
    {
      src: 'https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/js/bootstrap.min.js',
      integrity: 'sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl',
      crossorigin: 'anonymous'
    }
  ]
})
</script>
  
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+Thai:wght@200;300&family=Inter:wght@300&family=Noto+Sans+Thai:wght@300&display=swap');

* {
  font-family: 'IBM Plex Sans Thai', sans-serif;
  font-family: 'Inter', sans-serif;
  font-family: 'Noto Sans Thai', sans-serif;
}
.navbar-brand {
  margin-left: 10px ;
}
.logo {
  margin-left: 10px ;
}
.content {
  margin-top: 5%;
}

.navbar-nav {
 font-size: 26px;
}
.nav-link:hover {
  color: gray;
}
.btn:hover{
  background: gray;
}
.icon-cart{
  margin-right: 30px;
}
</style>