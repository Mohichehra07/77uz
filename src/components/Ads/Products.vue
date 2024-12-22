<script setup>
import { ref, onMounted } from "vue";
import ProductItem from "./ProductItem.vue";
import { ads } from "@/constants/data";
import SkletLoading from "../UI/SkletLoading.vue";

const product = ref([]);
const loading = ref(false);

function loadProduct() {
  loading.value = true;
}

  setTimeout(() => {
    product.value = ads.map((item) => ({
      location: item.title,
      img: item.img,
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
  <div class="grid w-full grid-cols-2 gap-6 my-6 sm:grid-cols-3 lg:grid-cols-4 md:my-10" v-show="!loading">
    <ProductItem v-for="item in product" :key="item" />
  </div>
 <div
 class="grid pb-10 mt-10 md:grid-cols-2 lg:grid-cols-3 gap-x-10 gap-y-5" v-show="loading">
<SkletLoading type="product" v-for="i in 6" :key="i" v-show="loading" />
</div>
</template>