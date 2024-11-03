<template>
  <div>
    <MyComponent />
  </div>
</template>

<script>
import MyComponent from './components/MyComponent.vue';

export default {
  name: 'App',
  components: { MyComponent },
  data() {
    return {
      name: 'aasdasd',
    };
  },
};
</script>

<style></style>
