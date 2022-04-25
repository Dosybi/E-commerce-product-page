<script setup>
import ProductRating from './ProductRating.vue'
import ProductPrice from './ProductPrice.vue'
import ProductControls from './ProductControls.vue'
import ProductInfo from './ProductInfo.vue'
import ProductTitle from './ProductTitle.vue'
</script>
<script>
export default {
  data() {
    return {
      title: 'Пижама для девочек',
      art: '02765/46',
      rating: 4,
      feedback: 14,
      price: 800,
      priceOld: 1500,
      discount: [36, 20],
    }
  },
}
</script>

<template>
  <ProductTitle :title="title" :art="art" />
  <ProductRating :rating="rating" :feedback="feedback" />
  <ProductPrice :price="price" :priceOld="priceOld" :discount="discount" />
  <ProductControls :title="title" />
  <div class="product-info">
    <ProductInfo />
  </div>
</template>

<style scoped>
@media (min-width: 768px) {
  .product-info {
    display: block !important;
  }
}
@media (min-width: 650px) {
  .product-info {
    display: none;
  }
}
</style>
