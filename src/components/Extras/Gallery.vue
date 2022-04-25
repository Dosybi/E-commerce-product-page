<script>
export default {
  data() {
    return {
      images: [
        '/src/assets/image-gallery-1.png',
        '/src/assets/image-gallery-2.png',
        '/src/assets/image-gallery-3.png',
        '/src/assets/image-gallery-4.png',
        '/src/assets/image-gallery-5.png',
      ],
    }
  },
  methods: {
    showOverlay(e) {
      e.target.nextElementSibling.classList.remove('hidden')
    },
    hideOverlay(e) {
      setTimeout(() => {
        e.target.nextElementSibling.classList.add('hidden')
      }, 700)
    },
  },
}
</script>

<template>
  <div class="gallery">
    <div class="grid">
      <template v-for="(img, i) in this.images">
        <div :class="`gallery-item-${i + 1}`" alt="">
          <img
            :src="img"
            alt=""
            class="img"
            @mouseenter="showOverlay"
            @mouseleave="hideOverlay"
          />
          <div class="gallery-item-overlay hidden">
            <svg
              class="fullscreen"
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <rect
                x="4.5"
                y="6.5"
                width="13"
                height="13"
                rx="1.5"
                stroke="white"
              />
              <path
                d="M6.33784 6.63126L6.33784 6.49958C6.33784 5.39501 7.23327 4.49958 8.33784 4.49958L17.5 4.49959C18.6045 4.49959 19.5 5.39502 19.5 6.49959L19.5 15.9382C19.5 16.9853 18.5159 17.7537 17.5 17.4997V17.4997"
                stroke="white"
              />
            </svg>
            <svg
              width="48"
              height="48"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M7.74689 7.86865H16.2531C17.7116 7.86865 18.8604 9.11201 18.7453 10.566L18.2203 17.1975C18.1174 18.4977 17.0323 19.5002 15.7281 19.5002H8.27189C6.96769 19.5002 5.88261 18.4977 5.77968 17.1975L5.25468 10.5659C5.13958 9.11201 6.2884 7.86865 7.74689 7.86865Z"
                stroke="#ffffff"
              />
              <path
                d="M8.00005 12.5C8.00005 12.5 7.78335 4 12.0001 4C16.2168 4 16.0001 12.5 16.0001 12.5"
                stroke="#ffffff"
              />
            </svg>
            <div>Узнай, что на мне</div>
            <div class="likes">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M12.4287 7.25725L13.7612 5.03654L17.1965 5.46595L18.5 7.63849V10.3206L12.0145 18.1959L5.93879 10.2507L5.05635 8.04458L6.34556 5.89588L9.35445 4.60636L11.6159 7.32009L12.0666 7.86089L12.4287 7.25725Z"
                  fill="white"
                  stroke="white"
                />
                <path
                  d="M11.9 7.0948C10.6998 1.47892 1.40881 5.90389 5.76037 11.6018C10.1119 17.2996 12.4 19.4908 12.4 19.4908"
                  stroke="#333333"
                />
                <path
                  d="M11.8941 7.0948C13.0944 1.47892 22.7304 5.90389 18.3789 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
                  stroke="#333333"
                />
                <path
                  d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z"
                  fill="#333333"
                />
              </svg>
              <div>200</div>
            </div>
          </div>
        </div>
      </template>
    </div>
  </div>
</template>

<style>
.grid {
  width: 100%;
  display: grid;
  grid-template-areas:
    'i1 i1'
    'i2 i3'
    'i4 i5';
  grid-column-gap: 8px;
  position: relative;
}

@media (min-width: 650px) {
  .grid {
    grid-template-areas:
      'i1 i1 i2 i3'
      'i1 i1 i4 i5';
  }
}

.gallery-item-overlay {
  position: absolute;
  z-index: 2;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 98.5%;
  background: #333333;
  opacity: 0.7;
  color: #fff;
}

.fullscreen {
  position: absolute;
  top: 12px;
  right: 12px;
}
.likes {
  display: flex;
  position: absolute;
  bottom: 16px;
}
.gallery-item-1 {
  grid-area: i1;
}

.gallery-item-2 {
  grid-area: i2;
}

.gallery-item-3 {
  grid-area: i3;
}

.gallery-item-4 {
  grid-area: i4;
}

.gallery-item-5 {
  grid-area: i5;
}

.gallery-item-1,
.gallery-item-2,
.gallery-item-3,
.gallery-item-4,
.gallery-item-5 {
  cursor: pointer;
}

.img {
  width: 100%;
}
</style>
