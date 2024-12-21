<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    item: {
        descraption: String,
        phoneNumber: Number,
        img: String,
        location:String,
        cost:Number, 
    }
});
// const like = ref(false)
// const divice_id = ref(" ")
// async function addToSaved(id) {
// try {
// if ( !like.value) {
//   like.value =true;
//   const respone = await storeInstance.post(
//     `/favourite-product-create-by-id/`,
//     {
//       product:id,
//       deice_id: divice_id.value,
//     }
//   )
// }
// }
// }

</script>
<template>
  <div class="grid pb-10 mt-10 md:grid-cols-3 md:gap-3 lg:grid-cols-4 lg:gap-1 gap-x-8 gap-y-5 cotainerMain" v-show="!loading">
    <div
      class="w-[278px] h-[470px] border-gray-100 bg-white rounded-lg "
    >
      <div class="relative">
        <span
          class="absolute mt-3 ml-3 text-white text-[40px] icon-black-heart"
        ></span>
        <img class="cursor-pointer " :src="item.img" alt="products" />
      </div>
      <div class="w-[238px] h-[190px] cursor-pointer p-5">
        <div
          class="w-[100px] text-center h-7 bg-[#EAEDF0] m-2 text-[14px] text-[#63676C] p-1"
        >
          {{ item.location }}
        </div>
        <strong
          ><h1
            class="text-black text-[15px] hover:text-[#388FF3] transition-all duration-500 cursor-pointer h-18"
          >
            {{ item.descraption }}
          </h1></strong
        >
        <p class="text-[#8E9297] text-[12px]">{{ item.date }}</p>
        <h4 class="text-[#8E9297] text-[12px]">{{ item.phoneNumber }}</h4>
        <h2 class="flex gap-2">
          {{ item.cost }}
          <p class="text-[#388FF3]">UZS</p>

        </h2>
      </div>
    </div>
  </div>
</template>
