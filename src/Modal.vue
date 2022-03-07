<template>
  <h1>Question</h1>
  <button :class="{ active: modelValue }" @click="updateValue($event, true)">
    Oui !
  </button>
  <button
    :class="{ active: modelValue == false }"
    @click="updateValue($event, false)"
  >
    Non !
  </button>
</template>

<script setup lang="ts">
defineProps<{ modelValue: boolean | null }>();

const emit = defineEmits<{ e: 'update:modelValue'; value: boolean }>();

function updateValue(event: MouseEvent, value: boolean) {
  emit('update:modelValue', value);
}
</script>

<style scoped lang="scss">
.active {
  background-color: red;
}
</style>
