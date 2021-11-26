<template>
  <q-card>
    <h2>Child Deep</h2>
    <q-input
      v-model="formData.input1"
      label="input1"
    />
    <q-input
      v-model="formData.input2.hi"
      label="input2"
    />
  </q-card>
</template>

<script setup>
import {
  ref, defineProps, defineEmits, watch,
} from 'vue';

const props = defineProps({ modelValue: { type: Object, default: () => ({}) } });
const emit = defineEmits(['update:modelValue']);

const formData = ref({});

watch(
  () => props.modelValue,
  (newValue) => { formData.value = newValue; },
  { deep: true, immediate: true },
);

watch(
  () => formData,
  (newValue) => { emit('update:modelValue', newValue); },
  { deep: true },
);
</script>
