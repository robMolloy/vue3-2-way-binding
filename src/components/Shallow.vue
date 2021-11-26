<template>
  <q-card>
    <h2>Child Shallow</h2>
    <q-input
      v-model="formData.input1"
      label="input1"
    />
    <q-input
      v-model="formData.input2"
      label="input2"
    />
  </q-card>
</template>

<script setup>
import { computed, defineProps, defineEmits } from 'vue';

const props = defineProps({ modelValue: { type: Object, default: () => ({}) } });
const emit = defineEmits(['update:modelValue']);

const formData = computed({
  get: () => props.modelValue,
  set: (value) => emit('update:modelValue', value),
});
</script>
