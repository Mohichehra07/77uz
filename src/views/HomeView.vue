<script setup>
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";
import card from "@/components/Ads/card.vue";
import Categories from "@/components/Category/Categories.vue";

</script>

<template>
  <div class="bg-[#F0F3F7]">
    <Navbar />
    <div>
      <Categories  />
      <card />
        
      
    </div>
    <Footer  />
  </div>
</template>