<template>
    <div class="fullscreen-modal" v-if="isOpen">
      <div class="modal-content">
        <button @click="closeModal" class="close-button">Закрыть</button>
        <slot></slot>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    props: {
      isOpen: Boolean,
    },
    methods: {
      closeModal() {
        this.$emit('close');
      },
    },
  });
  </script>
  
  <style scoped>
  /* Стили для модального окна на весь экран */
  .fullscreen-modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999; /* Выставьте z-index, чтобы окно находилось поверх остальных элементов */
  }
  
  .modal-content {
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
    position: relative;
    width: 80%; /* Ширина модального окна */
    max-width: 800px; /* Максимальная ширина модального окна */
  }
  
  .close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    cursor: pointer;
  }
  </style>
  