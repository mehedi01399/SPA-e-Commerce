<template>
  <div>
    
  <div class="header flex justify-between">
    <div class="w-1/6 text-center">
      <button class="text-3xl px-3 py-1" v-on:click="Toggle = !Toggle">
        <img src="./assets/close.svg" class="h-10 w-16 mt-2" v-if="Toggle" />
        <img src="./assets/menu.svg" class="h-8 w-12 mt-3"  v-else/>
      </button>
    </div>
    <div class="input-group w-full">
      <input
        type="search"
        class="input"
        placeholder="Search Anything..."
        @focus="visible"
      />
      <button class="search-btn">
        <img src="./assets/search.svg" />
      </button>
    </div>
    <div class="w-1/6 text-center -mt-3">
      <button class="text-4xl" v-on:click="navigateTo('cart')">
        <img src="./assets/cart.png" class="h-16 w-16 mt-2"/>
        <div class="absolute text-xs text-red-500">{{cart.length}}
        </div>
      </button>
      
    </div>
  </div>
  <div :class="{ 'menu-card ': true, 'menu-visible': menuVis }">
    <div
      class="w-full flex flex-wrap sm:divide-y sm:divide-x-0 lg:divide-y-0 xl:divide-x divide-gray-300"
    >
      <div class="lg:w-1/4 w-full h-full">
        <div class="menu-title">Menu</div>
      </div>
      <div class="lg:w-3/4 w-full h-full p-2">
        <div class="menu-title">Search Result</div>
        <ul>
          <li class="border-b border-b-1 px-1 py-2">
            <a href="#" class="text-blue-500">All Result</a> 20 results found
          </li>
          <li class="border-b border-b-1 px-1 py-2">
            <a href="#" class="text-blue-500">Category 1</a> 20 results found
          </li>
          <li class="border-b border-b-1 p-1">
            <a href="#" class="text-blue-500">Category 2</a> 20 results found
          </li>
        </ul>
      </div>
    </div>
  </div>
  <button
    @click="menuVis = false"
    :class="{ backdrop: true, 'bd-visible': menuVis }"
  ></button>
      <div class="menu-card">
        <div class="mt-16 mb-32 duration-500 lg:duration-75 fixed top-0 left-0 h-full w-0 sidepanel overflow-x-hidden" v-bind:class="[Toggle?'w-2/3 lg:w-full':'w-0']">
          <div class="flex flex-col delay-700 ml-5">
            <div role="toggle" class="p-6 mega-menu left-0 absolute w-full mb-16 sm:mb-0 shadow-xl  bg-gray-100 overflow-hidden">
            <div class="mx-auto w-full sm:flex justify-between mx-2 mt-3">
              <ul class="px-4 w-full sm:w-1/2 lg:inline-block border-gray-600 border-b sm:border-r lg:border-b-0 pb-6 pt-6 lg:pt-3">
                <button class="font-bold text-xl text-black text-bold mb-2">Menu</button>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Home</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Shop</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Blog</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Contact</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">About</a>
                </li>
              </ul>
              <ul class="px-4 w-full sm:w-1/2 lg:inline-block border-gray-600 border-b sm:border-r-0 lg:border-r lg:border-b-0 pb-6 pt-6 lg:pt-3">
                <h3 class="font-bold text-xl text-black text-bold mb-2">Category</h3>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Men's  Product</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Women's  Product</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Kid's  Product</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Digital  Product</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Others  Product</a>
                </li>
              </ul>
              <ul class="px-4 w-full sm:w-1/2 lg:inline-block border-gray-600 border-b sm:border-b-0 sm:border-r md:border-b-0 pb-6 pt-6 lg:pt-3">
                <h3 class="font-bold text-xl text-black text-bold mb-2">Best Selling Items</h3>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Eid Special Panjabi</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Puja Special Sharee</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Summer Special T-Shirt</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Winter Special Jacket</a>
                </li>
                <li>
                  <a href="#" class="block p-3 bg-gradient-to-r from-yellow-600 to-blue-500 hover:from-pink-500 hover:to-orange-500 text-white font-semibold">Covid-19 Special Watch</a>
                </li>
              </ul>
              <ul class="px-4 w-full sm:w-1/2 lg:inline-block border-gray-600 pb-6 pt-6 lg:pt-3">
                <h3 class="font-bold text-xl text-black text-bold mb-2">CEO and Founder</h3>
                <li class="pt-3">
                  <img src="https://avatars3.githubusercontent.com/u/56244543" width="200">
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
      
    <div v-if="page === 'cart'">
      <Cart v-on:removeItemFromCart="removeItemFromCart" :cart="cart" />
    </div>

    <div v-if="page === 'products'">
      <Products v-on:addItemToCart="addItemToCart" />
    </div>
  </div>
</template>

<script>
import Products from "./components/Products.vue";
import Cart from "./components/Cart.vue";
export default {
  name: "App",
  data: () => {
    return {
      page: "products",
      cart: [],
      menuVis: false,
        Toggle: false,
        menu:false
    };
  },
  methods: {
    visible() {
      this.menuVis = true;
    },
    addItemToCart(product) {
      this.cart.push(product);
    },
    removeItemFromCart(product) {
      this.cart.splice(this.cart.indexOf(product), 1);
    },
    navigateTo(page) {
      this.page = page;
    }
  },
  components: { Products, Cart }
};
</script>
