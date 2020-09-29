<template>
  <div class="div-card">
    <div class="flex justify-between">
      <div class="lg:w-1/4 w-8/12 overflow-hidden">
        <img src="https://i.insider.com/561d30b99dd7cc1a008c1522" :alt="property.imageAlt" class="product-image">
      </div>
      <div class="lg:w-1/4 w-6/12 p-1">
        <div class="w-full">
          <div class="text-gray-600 text-xs uppercase font-semibold tracking-wide">Ferrari F12</div>
          <h4 class="font-semibold text-lg leading-tight truncate mt-1">$ 1,00,000</h4>
        </div>
      </div>
      <div class="w-1/3 flex flex-col text-center p-1">
          <div class="w-full">
            <button class="border rounded h-12 w-full p-1">
              <input type="number" v-model="num" class="text-center">
            </button>
          </div>
          <div class="w-full flex mt-1">
            <button class="w-full border rounded h-8 w-8 mr-1" v-on:click="num++">
              <span class="text-xl"><i class="fal fa-plus text-black"></i></span>
            </button>

            <button class="w-full border rounded h-8 w-8 ml-1" v-on:click="num--" :disabled="num == 0">
              <span class="text-xl"><i class="fal fa-minus"></i></span>
            </button>
          </div>
      </div>
    </div>
  </div>
      <div class="w-full flex flex-col text-center p-1 -mt-8">
          <div class="dropdown inline-block relative mt-auto">
            <button v-on:click="Dropdown = !Dropdown">Details<i class="fas fa-angle-down"></i></button>
            <ul class="dropdown-menu absolute text-gray-700 pt-1 bg-white w-full shadow-md rounded" v-bind:class="[Dropdown?'block':'hidden']">
              <li class=""><a class="" href="#">One</a></li>
              <li class=""><a class="" href="#">Two</a></li>
              <li class=""><a class="" href="#">Three is the magic number</a></li>
            </ul>
          </div>
      </div>
</template>

<script>
//import ProductInfo from "./ProductInfo"
export default {
  data(){
    return{
      num:0,
      Dropdown:false
    }
  },
  props: {
    property: Object
  }
}
</script>

<style>
</style>