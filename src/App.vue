<script setup>
import { ref } from "vue";
import socksGreenImage from './assets/images/socks_green.jpeg'

// 'ref' for simpler data
const product = ref("Socks");
const image = ref(socksGreenImage);
const inStock = ref(true)
const details = ref(['50% cotton', '30% wool', '20% polyester'])
const variants = ref([
  {id: 2234, color: 'green'},
  {id: 2235, color: 'blue'}
])

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
  <div class="nav-bar"></div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <img :src="image"
      </div>

      <div class="product-info">
        <h1>{{ product }}</h1>
        <p v-if="inStock">In Stock</p>
        <p v-else>Out Stock</p>
        <ul>
          <li v-for="detail in details">{{ detail }}</li>
        </ul>
        <div v-for="variant in variants" :key="variant.id">{{ variant.color }}</div>
      </div>
    </div>
  </div>
</template>
