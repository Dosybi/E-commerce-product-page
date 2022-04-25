<script setup>
import IconPerson from '../icons/IconPerson.vue'
import IconFavorite from '../icons/IconFavorite.vue'
import IconBag from '../icons/IconBag.vue'
import IconMenu from '../icons/IconMenu.vue'
</script>
<script>
export default {
  methods: {
    showMenu() {
      document.querySelector('.menu-mobile').classList.remove('hidden')
      document.querySelector('.menu-mobile-wrapper').classList.remove('hidden')
    },
    hideMenu() {
      document.querySelector('.menu-mobile').classList.add('hidden')
      document.querySelector('.menu-mobile-wrapper').classList.add('hidden')
    },
  },
}
</script>

<template>
  <header class="header">
    <div class="menu-mobile hidden">
      <svg
        class="close"
        width="24"
        height="24"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        @click="hideMenu"
      >
        <path d="M3.69995 12.0664L12.05 3.88337" stroke="#333333" />
        <path d="M12.2516 12.0664L3.90154 3.88335" stroke="#333333" />
      </svg>
      <div class="menu-mobile-item">постельное белье</div>
      <div class="menu-mobile-item">одежда для дома</div>
      <div class="menu-mobile-item">Одежда для улицы</div>
      <div class="menu-mobile-item">ВЫход</div>
    </div>
    <div class="menu-mobile-wrapper hidden" @click="hideMenu"></div>
    <img
      alt="Logo"
      class="logo"
      src="@/assets/logo.svg"
      width="67"
      height="16"
    />

    <div class="wrapper">
      <nav class="nav-desktop">
        <div class="nav-desktop-item">постельное белье</div>
        <div class="nav-desktop-item">одежда для дома</div>
        <div class="nav-desktop-item">Одежда для улицы</div>
        <div class="nav-desktop-item">ВЫход</div>
      </nav>
    </div>

    <div class="wrapper">
      <nav>
        <span class="nav-item">
          <IconPerson />
        </span>
        <span class="nav-item">
          <IconFavorite />
        </span>
        <span class="nav-item">
          <IconBag />
        </span>
        <span class="nav-item">
          <IconMenu @click="showMenu" />
        </span>
      </nav>
    </div>
  </header>
</template>

<style scoped>
@media (min-width: 768px) {
  .nav-item:nth-last-of-type(1) {
    display: none;
  }
}

@media (max-width: 900px) {
  .nav-desktop-item {
    font-size: 0.7rem;
  }
}

.menu-mobile-wrapper {
  position: absolute;
  inset: 288px 0 0 0;
  height: 100vh;
  z-index: 1000;
}
.nav-desktop {
  display: flex;
  align-items: center;
  align-content: center;
  font-size: 14px;
  text-transform: uppercase;
}
.nav-desktop-item {
  cursor: pointer;
}
.nav-desktop-item::before {
  left: 0;
  bottom: 0;
  width: 100%;
  height: 1px;
  background: #e600e6;
  transform: scaleX(0);
  content: '';
  position: absolute;
  transition: transform 0.5s ease;
}
.nav-desktop-item:hover::before {
  transform: scaleX(1);
}
.nav-desktop-item:not(:nth-last-of-type(1)) {
  margin-right: 2rem;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 4.8rem;
  margin: 0;
  padding: 18px 20px 26px 20px;
  position: sticky;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  background: #fff;
}

nav {
  display: flex;
  justify-content: center;
}
.nav-item {
  cursor: pointer;
}
.nav-item:hover {
  transition: transform 125ms;
  transform: translateY(-2px);
}
.nav-item:not(:nth-last-of-type(1)) {
  margin-right: 1.5rem;
}
.menu-mobile {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1000;
  background: #fff;
  width: 100%;
  padding: 80px 20px 30px 30px;
}
.close {
  position: absolute;
  top: 18px;
  right: 10px;
  cursor: pointer;
}
.menu-mobile-item {
  text-transform: uppercase;
  cursor: pointer;
}
.menu-mobile-item:hover {
  background: #fefefe;
}
.menu-mobile-item:not(:last-of-type) {
  margin-bottom: 30px;
}

@media (max-width: 768px) {
  .nav-desktop {
    display: none;
  }
}
</style>
