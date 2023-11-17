<script setup lang="ts">
import { ref } from "vue";
import { SwipeModal } from "@takuma-ru/vue-swipe-modal";

const isOpen = ref(false);
</script>

<template>
  <main>
    <a href="https://vue-swipe-modal-docs.takumaru.dev/" target="_blank">
      <img
        src="https://user-images.githubusercontent.com/49429291/182005504-0567f54a-80e3-4a31-ba5b-740db91b5190.png"
        alt="vue swipe modal logo"
        :class="[$style['logo'], $style['vue']]"
      />
    </a>
    <h3>@takuma-ru/vue-swipe-modal</h3>
    <button @click="isOpen = true">Open modal</button>
    <SwipeModal v-model="isOpen" :class="$style['modal']">
      <button @click="isOpen = false">Open modal</button>
      <template v-for="i in 10">
        <p>Swipe me {{ i }} times</p>
      </template>
    </SwipeModal>
  </main>
</template>

<style lang="scss" module>
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.modal {
  box-sizing: border-box;
  width: 100%;
  height: 50dvh;
  color: white;
  background-color: #1d1b20;
  border-radius: 1rem 1rem 0 0;
}
</style>
