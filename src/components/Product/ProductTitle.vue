<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    art: {
      type: String,
    },
  },
}
</script>

<template>
  <h1>{{ title }}</h1>
  <div class="part-number">{{ `Арт. ${art}` }}</div>
</template>

<style scoped>
h1 {
  font-weight: 600;
  font-size: 18px;
  margin: 20px 0 0 0;
}

.part-number {
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;
  color: #828282;
  margin: 0 0 18px 0;
}

@media (min-width: 650px) {
  h1 {
    margin: 0;
  }
}
</style>
