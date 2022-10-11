<template>
  <div>
    <button @click="open()">open modal</button>
    <swipe-modal
      v-model="modal"
      contents-height="80vh"
      border-top-radius="16px"
      @close="close()"
    >
      <h3>For PC</h3>
      <p>Drag and drop the chip at the top of the modal.</p>
      <h3>For SP</h3>
      <p>Swipe down the modal.</p>
    </swipe-modal>
  </div>
</template>

<script setup lang="ts">
import swipeModal from '@takuma-ru/vue-swipe-modal';
import { ref } from 'vue';

const modal = ref(false);

const open = () => {
  modal.value = true;
};

const close = () => {};
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
