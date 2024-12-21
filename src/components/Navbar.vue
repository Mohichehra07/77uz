<script setup>
import { ref } from 'vue';
import Modal from '../components/Modal/Modal.vue';
import { firstModal } from '@/constants/data';


const isOpenModal = ref(false);

const openModal = () =>{
  isOpenModal.value = true;
};

const closeModal = () =>{
  isOpenModal.value = false;
}

</script>
<template>
  <div
    class="flex justify-between w-full h-20 bg-white pl-[328px] pt-7 pb-7 pr-[328px] mb-[100px]"
  >
    <div class="flex items-center justify-center gap-6">
      <div class="w-[110px] h-6 flex">
        <img
          class="w-5 h-5"
          src="../../public/language/ruLanguage.png"
          alt="flag"
        />
        <select>
          <option value="ru">Русский</option>
          <option value="uz">O'zbek</option>
        </select>
      </div>
      <div
        class="text-gray-400 cursor-pointer hover:text-blue-500 w-[150px] h-5 flex"
      >
        <span class="icon-phone"></span>
        <p>+998 88 500 50 00</p>
      </div>
    </div>
    <div>

      <router-link
        to="/"
        class="absolute top-0 left-[50%] -translate-x-1/2 bg-white border border-t-0 border-gray-4 rounded-b-[20px] p-3 md:px-4 md:py-3 shadow-3xl"
      >
        <img
          class="max-md:h-12"
          src="../../public/logo/logo.png"
          alt="logo"
        />
      </router-link>

    </div>
    <div class="flex items-center justify-center gap-6">
      <div>
        <div
          class="flex items-center justify-center gap-1 text-black transition-all cursor-pointer hover:text-blue-400"
        >
          <span class="icon-blue-heart"></span>
          <p>Избранные</p>
        </div>
      </div>
      <button  @click="openModal"
       class="w-[118px] h-[40px] text-black border border-black rounded-sm hover:bg-slate-300 transition-all duration-500"
      >
        Войти
        <span class="icon-exit"></span>
      </button>
    </div>
  </div>
   <!--Modal -->

   <Modal :is-open="isOpenModal" @close="closeModal">
    <div v-for="data in firstModal" :key="data">
      <strong> <h1> {{ data.title }} </h1> </strong>
      <p class="text-[12px] text-[#8E9297]"> {{ data.text }} </p><br>

      <form action="registartion">
        <label for="login">
          {{ data.loginLable }}
          <input class="w-[338px] h-[44px] bg-[#F0F3F7] rounded-lg text-[14px] text-[#B8BBBD]" type="text" placeholder="Введите логин" required>
        </label>
        <label for="password">
          {{ data.passLable }} 
          <input class="w-[338px] h-[44px] bg-[#F0F3F7] rounded-lg text-[14px] text-[#B8BBBD] " minlength="8"  type="password" placeholder="Введите пароль" required>
        </label><br>
        <router-link class="text-[#388FF3] text-[12px]" to="#">{{data.parol}}</router-link><br><br>

        <button class="border-none bg-[#388FF3] m-2 text-[white] w-[338px] h-[44px] rounded-lg"> {{ data.login }} </button>
        <h3 class="text-[#8E9297] text-[12px] text-center"> {{ data.want }} </h3>
        <button class="border m-2 border-blue-500 text-[#388FF3] w-[338px] h-[44px] rounded-lg"> {{ data.sumbit }} </button>
        
      </form>
      
    </div>
   </Modal>
</template>
