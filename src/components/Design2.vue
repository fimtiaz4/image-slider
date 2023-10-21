<script setup>
import { ref } from "vue";
import { images } from "../data/data";
let indexs = ref(0);
</script>

<template>
  <img :src="images[indexs].thumb" alt="" />
  <p>{{ indexs + 1 }} / {{ images.length }}</p>
  <button @click="indexs <= 0 ? (indexs = images.length - 1) : indexs--">Left</button>
  <button @click="indexs < images.length - 1 ? indexs++ : (indexs = 0)">Right</button>
</template>

<style scoped></style>
