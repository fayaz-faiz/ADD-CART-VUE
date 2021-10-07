  <template>
    <div>
      <h1>Products</h1> 
      <div class="products">
        <div v-for="(product, index) in products" :key="index">
          <h3>{{product.name}}</h3>
          <div class="cost">{{product.cost}}</div>
          <img :src="product.image" />
          <button v-on:click="addItemToCart(product)">Add to cart</button>
           <div>
        <button v-on:click="removeItemFromCart(product)">-</button>
        <input type="number" value="0">
      <button v-on:click="addItemToCart(product)">+</button>
          

           </div>
        </div>
      
      </div>
    </div>
  </template>

  <script>
  export default {
    data: () => {
      return {
        products: [
          {
            name: "Noise Airpods plus",       
            cost: 2500,
            image: "http://cdn.shopify.com/s/files/1/0997/6284/products/4_58dcaaa9-ff0a-420a-9539-5b62242fa581_grande.png?v=1632217054"
              
          },
          {
            name: "Noise Fit Active SpO2 Smartwatch  (Grey Strap, Regular)",
            cost:   3500,
            image: "https://rukminim1.flixcart.com/image/416/416/kolsscw0/smartwatch/e/e/v/wrb-sw-active-std-gry-android-ios-noise-original-imag3f7qzpfsw2b9.jpeg?q=70"
            
          },
          {
            name: "Puma Running Shoe",
            cost: 1500,
            image: "https://rukminim1.flixcart.com/image/880/1056/kg9qbgw0-0/shoe/7/r/e/380815-puma-white-black-original-imafwgy4sgzuznj6.jpeg?q=50"
            
          },
          {
            name:"Iphone 12 pro max",
            cost:192000,
            image:"https://rukminim1.flixcart.com/image/416/416/kg8avm80/mobile/r/h/z/apple-iphone-12-dummyapplefsn-original-imafwg8duby8qbn4.jpeg?q=70"
          },
          {
            name:"HP Pavilion Ryzen 7 Octa Core 5800H - (16 GB/512 GB SSD/Windows 10",
            cost:75000,
            image:"https://rukminim1.flixcart.com/image/416/416/kbqu4cw0/computer/q/x/r/hp-original-imaftyzazfjd2gyb.jpeg?q=70"
          },
          {
            name:`OnePlus 7T Pro
90 Hz Display
Smooth Like Never Before
From ₹43,999`,
            cost:45000,
            image:"https://static.compareindia.news18.com/compareindia/gallery/images/2019/oct/oneplus7tpro(2)_171426464855.jpg"
          },
        ]
      };
    },
    methods: {
      addItemToCart(product) {
        this.$emit("addItemToCart", product);
      }
      
    },
    
  };  
  </script>

  <style scope>
    .products img{
      height: 250px;

    }
    h1{
      text-align: center;
      background: darksalmon;
    font-family: cursive;
    }
    .cost{
      font-size: 200%;
    }
    input{
      width: 25px;
      height: 30px;
    }
    
  </style>
