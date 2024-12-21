<!-- <script setup>
import { ref, onMounted } from "vue";
import { defineAsyncComponent } from "vue";
import { ads } from "@/constants/data";
import Card from "./card.vue";


const ProductCard = defineAsyncComponent(()=> import("./card.vue"));
const loading = ref(false);

function loadProduct() {
  loading.value = true;
}

  setTimeout(() => {
    ProductCard.value = ads.map((item) => ({
      location: item.title,
      // img: item.img,
      cost: item.cost,
      descraption:item.descraption,
      date: item.date,
      phoneNumber:item.phoneNumber,
    }));
    loading.value = false;
  }, 700);


onMounted(() => {
    loadProduct();
});


</script>

<template>
 <ProductCard  v-for="item in Card" :key="item"/>
</template> -->