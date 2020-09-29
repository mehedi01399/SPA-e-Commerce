<template>
  <div>
    <h1>Products</h1>
    <div class="mt-12">
      <div
        v-for="(product, index) in products"
        :key="index"
        class="div-card m-2"
      >
        <div class="justify-around flex">
          <img :src="product.image" class="w-24 h-24" />
          <div class="ml-1">
            <div
              class="text-gray-900 text-md capitalize font-black"
            >
              {{ product.name }}
            </div>
            <h4 class="font-semibold text-lg leading-tight truncate mt-1">
              {{ product.cost }}
            </h4>
          </div>
          <div class="m-auto mr-10">
            <button v-on:click="addItemToCart(product)">
              <i
                class="font-black text-lg text-white rounded-full h-10 w-10 flex items-center justify-center bg-red-500"
              >+</i>
            </button>
          </div>
            <div class="mt-auto mr-2">
              <button v-on:click="Dropdown = !Dropdown">
                <i class="fas fa-angle-down mt-auto"></i>
              </button>
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import json from "../assets/product.json";
export default {
  data() {
    return {
      products: json,
      Dropdown: false,
    };
  },
  methods: {
    addItemToCart(product) {
      this.$emit("addItemToCart", product);
    },
  },
};
</script>
