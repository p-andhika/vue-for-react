<script setup>
import { ref } from "vue";
import socksGreenImage from './assets/images/socks_green.jpeg'
import socksBlueImage from './assets/images/socks_blue.jpeg'

// 'ref' for simpler data
const product = ref("Socks");
const image = ref(socksGreenImage);
const inStock = ref(true)
const details = ref(['50% cotton', '30% wool', '20% polyester'])
const variants = ref([
  {id: 2234, color: 'green', image: socksGreenImage},
  {id: 2235, color: 'blue', image: socksBlueImage}
])
const cart = ref(0)

const addToCart = () => {
  cart.value += 1
}

const updateImage = (variantImage) => {
  image.value = variantImage
}

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
  <div class="cart">Cart {{ cart }}</div>
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
        <div
          v-for="variant in variants"
          :key="variant.id"
          v-on:mouseover="updateImage(variant.image)"
        >
          {{ variant.color }}
        </div>
        <button class="button" v-on:click="addToCart">Add to Cart</button>
      </div>
    </div>
  </div>
</template>
