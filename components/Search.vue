<template>
  <div>
    <input v-model="searchText" />
    <button type="button" @click="$emit('searchText', searchText)">Найти</button>
  </div>
</template>
<script>
import MyInput from './MyInput.vue';

export default {
  name: 'Search',
  data: {
    searchText: '',
  },
  components: { MyInput },
};
</script>
