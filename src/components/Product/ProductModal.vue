<script>
export default {
  methods: {
    close(e) {
      document.querySelector('.modal').classList.add('hidden')
    },
  },
}
</script>

<template>
  <div class="modal hidden" @click="close">
    <div class="modal-content">
      <p class="modal-text"></p>
      <svg
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        class="close"
        @click="close"
      >
        <path d="M3.69995 12.0664L12.05 3.88337" stroke="#C4C4C4" />
        <path d="M12.2516 12.0664L3.90154 3.88335" stroke="#C4C4C4" />
      </svg>
    </div>
  </div>
</template>

<style scoped>
.modal {
  display: block;
  position: fixed;
  z-index: 2000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgb(0, 0, 0);
  background-color: rgba(0, 0, 0, 0.4);
}

.modal-content {
  background-color: #fff;
  margin: 40vh auto;
  padding: 20px;
  width: 50%;
  display: flex;
  justify-content: space-between;
  border-radius: 10px;
}

.close {
  color: #333333;
  font-weight: bold;
  cursor: pointer;
  align-self: flex-start;
}
</style>
