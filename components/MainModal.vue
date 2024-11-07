<template>
  <div>
    <button @click="openModal">Open</button>
    <Modal
      v-if="isModalOpen"
      :close="isModalOpen"
      title="Окно"
      @close="isModalOpen = false"
    >
      <p>
        Здравствуйте! Готов приступить к работе. Сделаю в срок, со всеми
        доработками. Удобно связаться со мной в тг: @evgeny_chet или: tg:
        https://t.me/evgeny_chet vk: https://vk.com/evgeny_chet Моя последняя
        работа, включая адаптив: https://fusemonterey.com/
        http://digitalwomenclub.tilda.ws
        Здравствуйте! Готов приступить к работе. Сделаю в срок, со всеми
        доработками. Удобно связаться со мной в тг: @evgeny_chet или: tg:
        https://t.me/evgeny_chet vk: https://vk.com/evgeny_chet Моя последняя
        работа, включая адаптив: https://fusemonterey.com/
        http://digitalwomenclub.tilda.ws
      </p>
    </Modal>
  </div>
</template>
<script>
import Modal from './Modal.vue';

export default {
  components: { Modal },
  data() {
    return {
      isModalOpen: false,
    };
  },
  methods: {
    openModal() {
      this.isModalOpen = true;
    },
  },
};
</script>
<style scoped>
</style>
