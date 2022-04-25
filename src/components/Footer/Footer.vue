<script setup>
import FooterLinks from './FooterLinks.vue'
import FooterSubscribtion from './FooterSubscribtion.vue'
</script>

<template>
  <footer>
    <FooterLinks />
    <FooterSubscribtion />
  </footer>
</template>

<style scoped>
@media (min-width: 1024px) {
  footer {
    display: flex;
    align-items: flex-start;
    justify-content: space-around;
  }
}
footer {
  margin: 30px 20px 50px 20px;
}
</style>
