<script>
export default {
  props: {
    addToBasket: Function,
    addToFavorites: Function,
  },
}
</script>

<template>
  <div class="buttons-row">
    <input
      type="button"
      value="Добавить в корзину"
      class="buy"
      @click="addToBasket"
    />
    <button class="favorite" @click="addToFavorites">
      <svg
        class="favorite-icon"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M11.8999 7.0948C10.6997 1.47892 1.40869 5.90389 5.76025 11.6018C10.1118 17.2996 12.3999 19.4908 12.3999 19.4908"
          stroke="#ffffff"
        />
        <path
          d="M11.8941 7.0948C13.0943 1.47892 22.7304 5.90389 18.3788 11.6018C14.0272 17.2996 11.7 19.5 11.7 19.5"
          stroke="#ffffff"
        />
        <path
          d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z"
          fill="#ffffff"
        />
      </svg>
      <svg
        class="favorite-icon hidden"
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
          stroke="#ffffff"
        />
        <path
          d="M11.8941 7.0948C13.0944 1.47892 22.7304 5.90389 18.3789 11.6018C14.0273 17.2996 11.7 19.5 11.7 19.5"
          stroke="#ffffff"
        />
        <path
          d="M11.391 6.70752L12.4043 6.70757L12.3834 7.24079H11.391V6.70752Z"
          fill="#ffffff"
        />
      </svg>
    </button>
  </div>
  <div class="buy-link"><a href="#">Купить в 1 клик</a></div>
  <hr />
</template>

<style scoped>
@media (min-width: 768px) {
  hr {
    margin: 0px !important;
  }
}
.buttons-row {
  display: flex;
}
.buy {
  -webkit-appearance: none;
  -moz-appearance: none;
  outline: none;
  box-shadow: none;
  width: 203px;
  height: 44px;
  background: #333333;
  border: 1px solid #333333;
  color: #fff;
  font-size: 14px;
  margin-right: 4px;
  cursor: pointer;
}

.buy:hover,
.favorite:hover {
  background: #000000;
}
.favorite {
  -webkit-appearance: none;
  -moz-appearance: none;
  outline: none;
  box-shadow: none;
  width: 44px;
  height: 44px;
  background: #333333;
  border: 1px solid #333333;
  color: #fff;
  cursor: pointer;
  padding: 10px;
}
.buy-link {
  padding: 8px 0 12px 0;
  margin: 21px 0 17px 0;
}

hr {
  border: 0.5px solid #c4c4c4;
  margin-left: -20px;
}
</style>
