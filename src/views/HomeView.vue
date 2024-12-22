<script setup>
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";

import Categories from "@/components/Category/Categories.vue";
import Products from "@/components/Ads/Products.vue";
</script>

<template>
  <div class="bg-[#F0F3F7]">
    <Navbar />
    <div>
      <Categories  />
      <Products />  
      
    </div>
    <Footer  />
  </div>
</template>