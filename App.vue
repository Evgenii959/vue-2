<template>
  <div>
    <ProductList />
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue';

export default {
  name: 'App',
  components: { ProductList },
  data() {
    return {
      name: 'aasdasd',
    };
  },
};
</script>

<style></style>
