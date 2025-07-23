<script setup>
import { ref, reactive } from "vue";

const product = ref("Socks");
const product2 = reactive({
  name: "Socks",
});

setTimeout(() => {
  product.value = "New Socks";
  product2.name = "New Socks2";
}, 3000);
</script>

<template>
  <h1>{{ product }}</h1>
  <h1>{{ product2.name }}</h1>
</template>
