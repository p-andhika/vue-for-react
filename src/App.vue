<script setup>
import { ref, reactive } from "vue";

// 'ref' for simpler data
const product = ref("Socks");

// 'reactive' for big and complex data
// const product2 = reactive({
//   name: "Socks",
// });

// composable a.k.a custom hooks in react
// const useChangeWithDelay = function (state, newValue, delay) {
//   setTimeout(() => {
//     state.value = newValue;
//     // product2.name = "New Socks2";
//   }, delay);
// };

// useChangeWithDelay(product, "New Socks", 3000);
</script>

<template>
  <h1>{{ product }}</h1>
  <!-- <h1>{{ product2.name }}</h1> -->
</template>
