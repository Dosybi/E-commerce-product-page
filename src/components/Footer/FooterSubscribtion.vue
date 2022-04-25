<script>
export default {
  methods: {
    clearInput() {
      const input = document.querySelector('.subscribtion-input')
      input.value = ''
    },
    validateEmail() {
      const form = document.querySelector('.footer-subscribtion')
      const input = document.querySelector('.subscribtion-input')
      const message = document.querySelector('.subscribtion-message')
      const emailFormat = /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/
      if (input.value.match(emailFormat)) {
        form.classList.add('hidden')
        message.classList.remove('hidden')
        message.innerHTML = `<h2>Вы подписались на рассылку. Мы выслали подстверждение на ${input.value}</h2>`
      } else {
        message.classList.remove('hidden')
        message.innerHTML = `<h2>Пожалуйста, введите корректный адрес</h2>`
      }
    },
  },
}
</script>

<template>
  <div class="footer-subscribtion">
    <div class="footer-heading">Узнайте первыми о новинках и акциях</div>
    <div class="subscription">
      <input
        class="subscribtion-input"
        type="search"
        placeholder="Адрес электронной почты"
      />
      <svg
        class="cancel-button"
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        @click="clearInput"
      >
        <path d="M3.69995 12.0664L12.05 3.88337" stroke="#C4C4C4" />
        <path d="M12.2516 12.0664L3.90154 3.88335" stroke="#C4C4C4" />
      </svg>
    </div>
    <input
      class="subscribtion-btn"
      type="button"
      value="Подписаться"
      @click="validateEmail"
    />
  </div>
  <div class="subscribtion-message hidden"></div>
</template>

<style>
@media (min-width: 1024px) {
  .footer-subscribtion {
    margin-top: 12px !important;
    width: 30% !important;
  }
}
@media (min-width: 768px) {
  .footer-subscribtion {
    width: 75%;
  }
}
.footer-subscribtion {
  margin-top: 38px;
  display: flex;
  flex-direction: column;
}

.subscribtion {
  display: flex;
  align-items: center;
  position: relative;
}

.subscribtion-input {
  border: none;
  border-bottom: 1px solid #c4c4c4;
  width: 100%;
  font-size: 14px;
  color: #828282;
  padding: 4px 8px;
  margin: 16px 0 24px 0;
}

.subscribtion-input + svg {
  margin-left: -22px;
  margin-bottom: -2px;
}

.subscribtion-input:placeholder-shown + svg {
  visibility: visible;
}

.subscribtion-input::-webkit-search-cancel-button {
  -webkit-appearance: none;
}

.subscribtion-input:focus::-webkit-input-placeholder {
  opacity: 0;
}

.subscribtion-input:focus::-moz-placeholder {
  opacity: 0;
}

.subscribtion-input:focus:-ms-input-placeholder {
  opacity: 0;
}

.subscribtion-input:focus:-moz-placeholder {
  opacity: 0;
}

.cancel-button {
  cursor: pointer;
}

.subscribtion-input,
.subscribtion-btn {
  -webkit-appearance: none;
  -moz-appearance: none;
  outline: none;
  box-shadow: none;
}
.subscribtion-btn {
  width: 150px;
  height: 36px;
  background: #ffffff;
  border: 1px solid #333333;
  box-sizing: border-box;
  font-size: 14px;
  color: #333333;
  padding: 8px 28px;
  cursor: pointer;
  align-self: flex-end;
}
.subscribtion-btn:hover {
  background: #f2f2f2;
}

.subscribtion-message {
  margin-top: 20px;
}
</style>
