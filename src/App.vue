<template>
  <Modal v-model:agree="content" v-model:name.maj="name" />
  <p>{{ content }}</p>
  <p>{{ name }}</p>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import Modal from './Modal.vue';

const content = ref(null);
const name = ref('');
</script>

<style scoped lang="scss"></style>
