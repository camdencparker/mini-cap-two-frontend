<script>
import axios from "axios";
export default {
  data: function () {
    return {
      newProductParams: {},
      products: [],
    };
  },
  created: function () {},
  methods: {
    createProducts: function () {
      axios
        .post("/products", this.newProductParams)
        .then((response) => {
          console.log("products index", response);
          this.products = response.data;
          console.log(this.products);
        })
        .catch((error) => {
          console.log("Error", error.response);
          this.errors = error.response.data.errors;
        });
    },
  },
};
</script>

<template>
  <div>
    <h1>Create NEW PRODUCT</h1>
  </div>
</template>