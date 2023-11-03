<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar color="surface-variant" title="Application bar">
      <v-btn @click="openModal">Открыть форму</v-btn>
      <CardModal :is-open="isModalOpen" @close="closeModal">
        <CardForm />
      </CardModal>
    </v-app-bar>

    <v-navigation-drawer>
      <v-list>
        <v-list-item title="Drawer left"></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-navigation-drawer location="right">
      <v-list>
        <v-list-item title="Drawer right"></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main class="d-flex align-center justify-center flex-column" style="min-height: 300px;">
        <Card
        v-for="card in cards"
        :key="card.id"
        :title="card.title"
        :content="card.content"
        ></Card>
    </v-main>
  </v-layout>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import Card from './Card.vue';
import CardModal from './CardModal.vue'
import CardForm from './CardForm.vue'


export default defineComponent({
  components: {
    Card,
    CardModal,
    CardForm,
  },
  methods: {
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
    },
  },
  data() {
    return {
      isModalOpen: false,
      cards: [
        { id: 1, title: 'Карточка 1', content: 'Содержимое карточки 1' },
        { id: 2, title: 'Карточка 2', content: 'Содержимое карточки 2' },
        { id: 3, title: 'Карточка 3', content: 'Содержимое карточки 3' },
        { id: 4, title: 'Карточка 4', content: 'Содержимое карточки 4' },
        { id: 4, title: 'Карточка 4', content: 'Содержимое карточки 4' },
        { id: 4, title: 'Карточка 4', content: 'Содержимое карточки 4' },
        { id: 4, title: 'Карточка 4', content: 'Содержимое карточки 4' },
        { id: 4, title: 'Карточка 4', content: 'Содержимое карточки 4' },
        { id: 4, title: 'Карточка 4', content: 'Содержимое карточки 4' },
      ]
    }
  }
})
</script>