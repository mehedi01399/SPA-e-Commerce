<template>
  <div>
    <h1>Cart</h1>
    <div class="mt-12">
      <div v-for="(product, index) in cart" :key="index" class="div-card m-2">
        <div class="flex justify-between">
          <img :src="product.image" class="w-24 h-24"/>
          <div class="w-full ml-1">
            <div class="text-gray-900 text-md capitalize font-black tracking-wide">{{product.name}}</div>
            <h4 class="font-semibold text-lg leading-tight truncate mt-1">{{product.cost}}</h4>
          </div>
          
          <div class="w-full text-right p-2 m-auto mr-10">
            <button v-on:click="removeItemFromCart(product)">
              <i
                class="text-lg text-white rounded-full h-10 w-10 flex items-center justify-center bg-red-500"
              >X</i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["cart"],
  methods: {
    removeItemFromCart(product) {
      this.$emit("removeItemFromCart", product);
    }
  }
};
</script>