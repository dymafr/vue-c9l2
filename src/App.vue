<template>
  <Modal v-model="content" />
  <p>{{ content }}</p>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import Modal from './Modal.vue';

const content = ref(null);
</script>

<style scoped lang="scss"></style>
