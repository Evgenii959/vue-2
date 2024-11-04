<template>
  <div class="main">
    <div>
      <h1>Письменные столы</h1>
      <Search @searchText='searchProducts' />
    </div>
    <ul v-for="(table, index) in tables" :key="index">
      <ProductItem :table="table" @addBusket="addBusket(index)" />
    </ul>
  </div>
</template>
<script>
import ProductItem from './ProductItem.vue';
import MyInput from './MyInput.vue';
import Search from './Search.vue';

export default {
  name: 'ProductList',
  components: { ProductItem, MyInput, Search },
  data() {
    return {
      tables: [
        {
          name: 'Стол Джим',
          price: 1999,
          amount: 30,
        },
        {
          name: 'Стол Monaco',
          price: 19995,
          amount: 20,
        },
        {
          name: 'Стол Rome',
          price: 19999,
          amount: 10,
        },
      ],
    };
  },
  methods: {
    addBusket(index) {
      console.log(index);
    },
    searchProducts(searchText) {
      console.log('Загрузить товары:', searchText);
    },
  },
};
</script>
<style lang="scss" scoped></style>
