<template>
  <div class="home">
    <ProductDescriptionDrawer 
    :product="product"
    :active="active.product_drawer" /> 
    <div class="-product-card-container">
      <ProductSummaryCard
        v-for="product in items"
        :key="product.id"
        :product="product"
        v-on:view-prodoct="viewProduct($event )" />
    </div>
  </div>
</template>

<script>
import items from "./data/items.js";
import ProductSummaryCard from '../components/products/ProductSummaryCard.vue'
import ProductDescriptionDrawer from '../components/products/ProductDescriptionDrawer.vue'
export default {
  name: "Home",
  components: {
    ProductSummaryCard, ProductDescriptionDrawer
  },
  data() {
    return {
      items: items,
      product: null,
      active: {
        product_drawer: false 
      }
    };
  },
  method: {
     viewProduct(product) {
      this.product = product
     }
  }
};
</script>
