<script setup>
import IconClothes from '../icons/IconClothes.vue'
import IconCloc from '../icons/IconClock.vue'
import IconPay from '../icons/IconPay.vue'
</script>

<template>
  <div class="product_info">
    <div class="product_info_row">
      <IconClothes />
      <div><a href="#">Описание товара</a></div>
    </div>
    <div class="product_info_row">
      <IconCloc />
      <div><a href="#">Доставка и возврат</a></div>
    </div>
    <div class="product_info_row">
      <IconPay />
      <div><a href="#">Способы оплаты</a></div>
    </div>
  </div>
</template>

<style scoped>
.product_info {
  margin: 24px 0 24px 0;
}
.product_info_row {
  display: flex;
  align-items: center;
  margin-bottom: 12px;
}
.product_info_row > div {
  margin-left: 4px;
}
</style>
