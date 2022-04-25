<script>
export default {
  data() {
    return {
      options: [
        { text: 'Выбрать размер', value: '' },
        { text: 'XS', value: 'XS' },
        { text: 'S', value: 'S' },
        { text: 'M', value: 'M' },
        { text: 'L', value: 'L' },
        { text: 'XL', value: 'XL' },
      ],
      selectedSize: '',
    }
  },
  methods: {
    setSize(e) {
      this.selectedSize = e.target.value
      this.getSize(this.selectedSize)
    },
  },
  props: {
    getSize: Function,
  },
}
</script>

<template>
  <select @change="setSize" class="size-selector" required>
    <option :value="options[0].value" disabled selected>
      {{ options[0].text }}
    </option>
    <option v-for="option in options.slice(1)" :value="option.value">
      {{ option.text }}
    </option>
  </select>
  <div><a href="#">Определить размер</a></div>
</template>

<style scoped>
.size-selector {
  -webkit-appearance: none;
  -moz-appearance: none;
  outline: none;
  width: 315px;
  height: 44px;
  border: 1px solid #333333;
  border-radius: 0;
  font-size: 14px;
  padding: 8px;
  margin-top: 20px;
  background: url('../../assets/IconArrowDownSwipe.svg') 96% / 8% no-repeat;
  cursor: pointer;
}

@media (max-width: 320px) {
  .size-selector {
    width: 280px;
  }
}

.size-selector:hover {
  background-color: #f2f2f2;
}

option {
  cursor: pointer;
}
div {
  padding-top: 8px;
}
</style>
