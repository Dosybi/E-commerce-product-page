<script>
export default {
  data() {
    return {
      selectedQuantity: 1,
    }
  },
  props: {
    getQuantity: Function,
  },
  methods: {
    setQuantity(e) {
      const minus = document.querySelector('.minus')
      const plus = document.querySelector('.plus')
      let quantity = document.querySelector('.quantity')
      if (e.target == minus && this.selectedQuantity > 1) {
        this.selectedQuantity -= 1
      }
      if (e.target == plus) {
        this.selectedQuantity += 1
      }
      quantity.value = this.selectedQuantity
      this.getQuantity(this.selectedQuantity)
    },
  },
}
</script>

<template>
  <div class="quantity-selector" @click="setQuantity">
    <input type="button" value="−" class="minus" /><input
      type="text"
      step="1"
      min="1"
      max=""
      name="quantity"
      value="1"
      class="quantity"
      disabled
    /><input type="button" value="+" class="plus" />
  </div>
</template>

<style scoped>
.quantity-selector {
  margin: 40px 0 15px 0;
}
.quantity {
  -webkit-appearance: none;
  -moz-appearance: none;
  outline: none;
  width: 49px;
  height: 44px;
  border: none;
  background: #f2f2f2;
  text-align: center;
  font-size: 14px;
}
.minus,
.plus {
  -webkit-appearance: none;
  -moz-appearance: none;
  outline: none;
  box-shadow: none;
  width: 49px;
  height: 44px;
  border: none;
  background: #f2f2f2;
  font-size: 14px;
  cursor: pointer;
}

.minus:hover,
.plus:hover {
  background: #e6e6e6;
}
</style>
