<script setup>
import ProductSizeSelector from './ProductSizeSelector.vue'
import ProductQuantitySelector from './ProductQuantitySelector.vue'
import ProductButtons from './ProductButtons.vue'
import ProductModal from './ProductModal.vue'
</script>
<script>
export default {
  props: {
    title: String,
  },
  data() {
    return {
      size: '',
      quantity: 1,
      favourite: false,
      added: false,
    }
  },
  methods: {
    getSize(selectedOption) {
      this.size = selectedOption
    },
    getQuantity(selectedQuantity) {
      this.quantity = selectedQuantity
    },
    addToBasket() {
      const modal = document.querySelector('.modal')
      const modalText = document.querySelector('.modal-text')
      modal.classList.remove('hidden')
      modalText.textContent = `Товар «${this.title}» в количестве ${
        this.quantity
      } единиц${this.quantity === 1 ? 'ы' : ''} добавлен в корзину`
    },
    addToFavorites(e) {
      this.added === false ? (this.added = true) : (this.added = false)
      const modal = document.querySelector('.modal')
      const modalText = document.querySelector('.modal-text')
      modal.classList.remove('hidden')
      const favoriteIcon = document.querySelectorAll('.favorite-icon')
      modalText.textContent = `Товар «${this.title}» ${
        this.added === false
          ? 'удалён из «Избранного»'
          : 'добавлен в «Избранное»'
      }`
      favoriteIcon.forEach((icon) =>
        icon.classList.contains('hidden')
          ? icon.classList.remove('hidden')
          : icon.classList.add('hidden')
      )
    },
  },
}
</script>

<template>
  <div>
    <ProductSizeSelector :getSize="getSize" />
    <ProductQuantitySelector :getQuantity="getQuantity" />
    <ProductButtons
      :addToBasket="addToBasket"
      :addToFavorites="addToFavorites"
    />
    <ProductModal />
  </div>
</template>

<style scoped></style>
