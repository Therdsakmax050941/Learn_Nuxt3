<template>
    <div class="container my-5">
      <h1 class="text-center my-4">About Us</h1>
      <div class="row align-items-center">
        <div class="col-md-6">
          <img src="https://via.placeholder.com/600" class="img-fluid rounded" alt="About Us Image" />
        </div>
        <div class="col-md-6">
          <p>
            Welcome to our e-commerce platform! Our mission is to provide high-quality products and excellent service to our customers. We believe in ensuring customer satisfaction and delivering the best online shopping experience.
          </p>
          <p>
            Connect with us for any inquiries or suggestions. Our customer support is available around the clock to assist you.
          </p>
          <p>
            <strong>Company Name</strong> <br />
            <strong>Address:</strong> 123 Main Street, Anytown, 12345 <br />
            <strong>Email:</strong> info@company.com <br />
            <strong>Contact:</strong> 123-456-7890
          </p>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  
  useHead({
    title: 'MyShop | About Us',
    meta: [{ name: 'description', content: 'An e-commerce platform providing high-quality products and excellent service' }],
  })
  </script>
  
  <style scoped>
    img {
      max-height: 100%;
    }
  
    p {
      font-size: 1.2em;
    }
  </style>
  