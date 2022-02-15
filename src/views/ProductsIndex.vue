<script>
import axios from "axios";
export default {
  data: function () {
    return {
      products: [],
    };
  },
  created: function () {
    this.indexProducts();
  },
  methods: {
    indexProducts: function () {
      axios.get("/products").then((response) => {
        console.log("products index", response);
        this.products = response.data;
        console.log(this.products);
      });
    },
  },
};
</script>
<template>
  <div>
    <h1>All Products</h1>
    <div v-for="product in products" :key="product.id">
      <h2>Name: {{ product.name }}</h2>
      <h3>Price: {{ product.price }}</h3>
      <h4>Description: {{ product.description }}</h4>
    </div>
  </div>
</template>