<template>
  <div class="footer-links">
    <div class="footer-links-col">
      <div class="footer-heading">покупателям</div>
      <div><a href="#">Каталог</a></div>
      <div><a href="#">Акции</a></div>
      <div><a href="#">Бренды</a></div>
    </div>
    <div class="footer-links-col">
      <div class="footer-heading">о нас</div>
      <div><a href="#">О компании</a></div>
      <div><a href="#">Новости</a></div>
      <div><a href="#">Команда</a></div>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .footer-links-col {
    width: 100% !important;
  }
  .footer-links-col:first-of-type {
    margin-right: 209px;
  }
}

.footer-links {
  padding: 12px 0 20px 0;
  display: flex;
}

.footer-links-col {
  width: 50%;
}

.footer-links-col :nth-child(2),
.footer-links-col :nth-child(3) {
  margin-bottom: 8px;
}

.footer-heading {
  font-size: 16px;
  text-transform: uppercase;
  margin-bottom: 12px;
}
</style>
