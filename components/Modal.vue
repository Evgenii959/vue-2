<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="modal" ref="modalBody" @scroll="onBodyScroll">
      <slot></slot>
    </div>
    <button :disabled="!isRulesReaded">Continue</button>
    <button @click="closeModal">Close</button>
  </div>
</template>
<script>
export default {
  name: 'Modal',
  props: {
    title: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      isRulesReaded: false,
    };
  },
  beforeCreate() {
    console.log('beforeCreate');
  },
  mounted() {
    const modalBody = this.$refs.modalBody;
    modalBody.scrollTop = modalBody.scrollHeight - modalBody.clientHeight;
  },
  methods: {
    closeModal() {
      this.$emit('close');
    },
    onBodyScroll() {
      const modalBody = this.$refs.modalBody;
      if (
        modalBody.clientHeight + modalBody.scrollTop >=
        modalBody.scrollHeight
      ) {
        this.isRulesReaded = true;
      }
    },
  },
};
</script>
<style scoped>
.modal {
  max-width: 200px;
  height: 200px;
  overflow-y: scroll;
}
</style>
