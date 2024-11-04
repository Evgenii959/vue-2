<template>
  <li>
    <h2>{{ table.name }}</h2>
    <p>{{ table.price }}</p>
    <p>{{ table.amount }}</p>
    <button @click="addBusket">Добавить в корзину</button>
  </li>
</template>
<script>
export default {
  name: 'ProductItem',
  props: ['table'],
  methods: {
    addBusket() {
      this.$emit('addBusket');
    },
  },
};
</script>
