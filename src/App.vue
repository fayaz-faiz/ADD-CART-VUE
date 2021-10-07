<template>
  <div>
    <header id="nav">
      <button v-on:click="navigateTo('products')">View products</button>
      {{cart.length}} ITEMS IN CART
      <button v-on:click="navigateTo('cart')">View Cart</button>
    </header>

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
      cart: []
    };
  },
  methods: {
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

<style>
body {
  
}
.products {
  display: grid;
  grid-template-columns: 1fr 1fr;
}
.products button {
  padding: 10px;
  background-color: rgb(216, 18, 18);
  color: white;
  outline: none;
  border: none;
  cursor: pointer;
}
</style>

<style scoped>
header {
  height: 60px;
  box-shadow: 2px 2px 5px rgb(255, 0, 0);
  background-image: linear-gradient(to right top, #d16ba5, #f76d8d, #ff7b6b, #ff9644,
   #f8b816, #f7ab0c, #f59f03, #f39200, #fb4630, #e7005b, #ad008a, #0f00af);  
  text-align: right;
  font-size: 30px;
  padding-top: 20px;
  position: sticky;
}
header button {
  padding: 10px;
  border: none;
  cursor: pointer;
  color: white;
  background-color: green;
}
#nav{
  top: 0%;
  position: sticky;
}
</style>
