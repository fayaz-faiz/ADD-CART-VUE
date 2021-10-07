<template>
  <div>
    <h1>Your Cart</h1>
    <div class="products">
      <div v-for="(product, index) in cart" :key="index">
        <h3>{{product.name}}</h3>
        <img :src="product.image" />
        <div>{{product.cost}}</div>
        <button v-on:click="removeItemFromCart(product)">Remove from cart</button>
      </div>
    </div>
  </div>
  <div>
    <h2>Total Price:-  {{gettotal}} </h2>
   
  </div>
</template>

<script>
import { } from '@vue/reactivity';
export default {
  props: ["cart"],
  methods: {
    removeItemFromCart(product) {
      this.$emit("removeItemFromCart", product);
    }
  },
 
 computed:{
   gettotal(){
     let sum = 0;

     this.cart.forEach(element => {
       sum+=element.cost 
       console.log('element',element);
       
     });
     return sum;
   }
 }
};
</script>

<style scoped>
h2{
  font-family: 'Courier New', Courier, monospace;
  text-align: center;
  background: aqua;
  width: 20%;
  margin-left: 30%;
}

</style>>