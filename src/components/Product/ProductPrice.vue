<script setup>
import IconArrowRightSwipe from '../icons/IconArrowRightSwipe.vue'
</script>
<script>
export default {
  props: {
    price: {
      type: Number,
      required: true,
    },
    priceOld: {
      type: Number,
      required: false,
    },
    discount: {
      type: [Number, Array],
      required: false,
    },
  },
}
</script>

<template>
  <div class="product_price">
    <div class="product_price-current">{{ `${price} ₽` }}</div>
    <div class="product_price-old">{{ `${priceOld} ₽` }}</div>
    <IconArrowRightSwipe />
  </div>
  <div class="discounts">
    <div v-for="item in this.discount" class="discounts_item">
      {{ `сикдка -${item}%` }}
    </div>
  </div>
</template>

<style scoped>
.product_price,
.discounts {
  display: flex;
  align-items: center;
}

.discounts {
  margin-bottom: 12px;
}
/* .product_price > div {
  margin-right: 12px;
} */
.product_price-current {
  font-weight: 700;
  font-size: 24px;
  line-height: 24px;
  text-transform: uppercase;
  margin: 8px 12px 8px 0;
}
.product_price-old {
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  text-decoration-line: line-through;
  color: #828282;
  margin: 11px 12px 9px 0;
}

.discounts_item {
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;
  padding: 4px 8px;
  border: 1px solid #333333;
  margin-right: 9px;
}
</style>
