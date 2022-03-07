<template>
  <h1>Question</h1>
  <button :class="{ active: agree }" @click="updateValue($event, true)">
    Oui !
  </button>
  <button
    :class="{ active: agree == false }"
    @click="updateValue($event, false)"
  >
    Non !
  </button>
  <hr />
  <input
    :value="name"
    @input="emit('update:name', ($event.target as HTMLInputElement).value)"
    type="text"
  />
</template>

<script setup lang="ts">
defineProps<{ agree: boolean | null; name: string }>();

const emit = defineEmits<{
  (e: 'update:agree', value: boolean);
  (e: 'update:name', value: boolean);
}>();

function updateValue(event: MouseEvent, value: boolean) {
  emit('update:agree', value);
}
</script>

<style scoped lang="scss">
.active {
  background-color: red;
}
</style>
