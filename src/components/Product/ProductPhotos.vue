<script>
export default {
  data() {
    return {
      images: [
        '/src/assets/image-product-1.png',
        '/src/assets/image-product-2.png',
        '/src/assets/image-product-3.png',
        '/src/assets/image-product-4.png',
        '/src/assets/image-product-5.png',
      ],
    }
  },
  methods: {
    switchMainImg(e) {
      const mainImage = document.querySelector('#main-image')
      const thumbnail = document.querySelectorAll('.thumbnail')
      mainImage.src = e.target.src
      thumbnail.forEach((img) => {
        img === e.target
          ? img.classList.add('active')
          : img.classList.remove('active')
      })
    },
  },
}
</script>

<template>
  <div class="product__gallery">
    <img
      :src="this.images[0]"
      alt="Product"
      class="main-image"
      id="main-image"
    />
    <div class="product__gallery_thumbs">
      <template v-for="(img, i) in this.images">
        <img
          :src="img"
          :alt="`Product photo ${i + 1}`"
          :class="i === 0 ? 'thumbnail active' : 'thumbnail'"
          @click="switchMainImg"
        />
        <div class="overlay"></div>
      </template>
    </div>
  </div>
</template>

<style scoped>
.main-image {
  width: 100%;
}

.product__gallery_thumbs {
  position: absolute;
  top: 28px;
  left: 24px;
  display: flex;
  flex-direction: column;
}

.thumbnail {
  width: 40px;
  margin-bottom: 4px;
}

.thumbnail:not(.active) {
  opacity: 0.8;
  filter: brightness(110%);
  cursor: pointer;
}

.thumbnail:hover {
  opacity: 1;
  filter: none;
}
@media (min-width: 768px) {
  .thumbnail {
    width: 70px;
    margin-bottom: 7px;
  }
}
</style>
