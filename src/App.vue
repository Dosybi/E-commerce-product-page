<script setup>
import Header from '@/components/Header/Header.vue'
import Product from '@/components/Product/Product.vue'
import Gallery from '@/components/Extras/Gallery.vue'
import Footer from '@/components/Footer/Footer.vue'
</script>
<script>
const body = document.body
let lastScroll = 0
window.addEventListener('scroll', () => {
  const currentScroll = window.pageYOffset
  if (currentScroll <= 0) {
    body.classList.remove('scroll-up')
    return
  }

  if (currentScroll > lastScroll && !body.classList.contains('scroll-down')) {
    body.classList.remove('scroll-up')
    body.classList.add('scroll-down')
  } else if (
    currentScroll < lastScroll &&
    body.classList.contains('scroll-down')
  ) {
    body.classList.remove('scroll-down')
    body.classList.add('scroll-up')
  }
  lastScroll = currentScroll
})
</script>

<template>
  <Header />
  <main>
    <Product />
  </main>
  <section>
    <div class="see-all"><a href="#">Посмотреть все стили</a></div>
    <Gallery />
  </section>
  <Footer />
  <div class="modal"></div>
</template>

<style>
@import '@/assets/base.css';

#app {
  max-width: 1390px;
  margin: 0 auto;
  padding: 0;
  font-weight: normal;
}
.see-all {
  text-align: center;
  margin: 33px 0 58px 0;
}

a {
  text-decoration: underline;
  color: #333333;
}
a:hover {
  color: #e600e6;
}

.hidden {
  display: none !important;
}

.scroll-down .header {
  transform: translate3d(0, -100%, 0);
}

.scroll-up .header {
  transform: none;
}

.scroll-up .header {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.35);
}
</style>
