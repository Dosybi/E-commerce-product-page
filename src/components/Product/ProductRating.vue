<script setup>
import IconArrowRightSwipe from '../icons/IconArrowRightSwipe.vue'
</script>
<script>
export default {
  props: {
    rating: {
      type: Number,
    },
    feedback: {
      type: Number,
    },
  },
  methods: {
    starsRender() {
      let stars = new Array(this.rating)
      let stars2 = new Array(5 - this.rating)
      stars.fill('★')
      this.rating != 5 ? stars.push(...stars2.fill('☆')) : null
      stars = stars.join('')
      console.log(stars)
      return stars
    },
  },
}
</script>

<template>
  <div class="product_rating">
    <div>Отзывы</div>
    <div>{{ starsRender() }}</div>
    <div>
      <a href="#">{{ `${feedback} отзывов` }}</a>
    </div>
    <IconArrowRightSwipe />
  </div>
</template>

<style scoped>
.product_rating {
  display: flex;
  margin-bottom: 20px;
}
.product_rating :nth-child(1) {
  margin-right: 13px;
}
.product_rating :nth-child(2) {
  margin-right: 4px;
}
.product_rating :nth-child(3) {
  margin-right: 8px;
}
</style>
