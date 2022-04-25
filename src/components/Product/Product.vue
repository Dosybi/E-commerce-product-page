<script setup>
import ProductPhotos from './ProductPhotos.vue'
import ProductContent from './ProductContent.vue'
import ProductInfo from './ProductInfo.vue'
</script>

<template>
  <section class="product">
    <div>
      <div class="product-photos">
        <ProductPhotos />
      </div>
      <div class="product-info">
        <ProductInfo />
      </div>
    </div>
    <div class="product-content">
      <ProductContent />
    </div>
  </section>
</template>

<style scoped>
@media (min-width: 768px) {
  .product-info {
    display: none;
  }
  .product-photos {
    width: 100%;
  }
}
@media (min-width: 650px) {
  .product {
    margin-right: 20px;
    display: flex;
  }
  .product-content {
    margin: 0;
  }
}

@media (max-width: 649px) {
  .product-info {
    display: none;
  }
}
.product-content {
  padding-left: 20px;
}
</style>
