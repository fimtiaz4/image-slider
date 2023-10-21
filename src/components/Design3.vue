<script setup>
import { ref } from "vue";
import { images } from "../data/data";
let indexs = ref(0);
const next = () => {
  indexs.value <= 0 ? (indexs.value = images.length - 1) : indexs.value--;
};
const prev = () => {
  indexs.value < images.length - 1 ? indexs.value++ : (indexs.value = 0);
};
const imgSelect = (index) => {
  indexs.value = index;
};
</script>

<template>
  <div class="flex flex-col items-center w-[800px]">
    <div class="flex justify-center">
      <button class="basis-1/6 justify-item-center text-black bg-orange-300 mr-5" @click="next()">Prev</button>
      <img class="basis-4/6" :src="images[indexs].full" alt="" />
      <button class="basis-1/6 text-black bg-orange-300 ml-5" @click="prev()">Next</button>
    </div>
    <p class="text-center py-5">{{ indexs + 1 }} / {{ images.length }}</p>
    <div class="flex justify-center">
      <img class="flex-auto mx-3 h-auto w-64" v-for="(image, index) in images" :key="index" :class="{ 'blur-sm': indexs !== index, 'blur-none': indexs === index }" @click="imgSelect(index)" :src="images[index].thumb" alt="" />
    </div>
  </div>
</template>

<style scoped></style>
