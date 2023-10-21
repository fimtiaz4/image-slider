<script setup>
import { ref } from "vue";
import { images } from "../data/data";
let indexs = ref(0);
</script>

<template>
  <img :src="images[indexs].thumb" alt="" />
  <p>{{ indexs + 1 }} / {{ images.length }}</p>
  <button v-show="indexs > 0" @click="indexs--">Left</button>
    <button v-show="indexs < images.length - 1" @click="indexs++">Right</button>
</template>

<style scoped></style>
