<template>
  <div class="home">
    <Nav />
    <Info :product="product" v-on:onCart="onCart" :plus="plus" :minus="minus" />
    <Tables :cart="cart" v-on:onCal="onCal"/>
  </div>
</template>

<script>
import Nav from "@/components/navigation_bar.vue";
import Info from "@/components/information.vue";
import Tables from "@/components/table.vue"

export default {
  name: "Home",
  components: {
    Nav,
    Info,
    Tables
  },
  methods: {
    onCart(value) {
      this.cart = value;
    },
    onPlus(plus){
      this.plus = plus
    }
  },
  data() {
    return {
      product: [
        {
          id: 1,
          picProduct:
            "https://d1a2ggqmhsoom.cloudfront.net/M7B2d4LbfHlGbxs7uYrZCMd1Dw8=/fit-in/236x345/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/umbro-3831-94523-1.jpg",
          nameProduct: "Umbro",
          price: 2590,
        },
        {
          id: 2,
          picProduct:
            "https://d1a2ggqmhsoom.cloudfront.net/BAyZPfRx-rVfQqq6pJycfrvGGRY=/fit-in/236x345/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/lotto-9898-40385-1.jpg",
          nameProduct: "Lotto",
          price: 990,
        },
        {
          id: 3,
          picProduct:
            "https://d1a2ggqmhsoom.cloudfront.net/GzRVxq0tFmaU0KKINCxVUqYAvBg=/fit-in/236x345/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/adidas-9866-11488-1.jpg",
          nameProduct: "Adidas",
          price: 4200,
        },
        {
          id: 4,
          picProduct:
            "https://d1a2ggqmhsoom.cloudfront.net/5zsh4MfIBv2Zr0sAIXINyFYN6M4=/fit-in/236x345/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/puma-7338-95468-1.jpg",
          nameProduct: "Puma",
          price: 699,
        },
        {
          id: 5,
          picProduct:
            "https://d1a2ggqmhsoom.cloudfront.net/LKi9l2__drAsFxAHOvrifI8aVow=/fit-in/236x345/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/nike-8569-85395-1.jpg",
          nameProduct: "Nike",
          price: 900,
        },
        {
          id: 6,
          picProduct:
            "https://d1a2ggqmhsoom.cloudfront.net/u8xIJrRXCADtAvkyaq0MjmAUMpo=/fit-in/236x345/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/mesuca-0769-88668-1.jpg",
          nameProduct: "Masuca",
          price: 699,
        },
      ],
      cart: [],
      plus:Number,
      minus:Number     
    };
  },
};
</script>
<style scoped>
</style>
