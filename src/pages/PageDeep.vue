<template>
  <q-page padding>
    <h1>Page Deep</h1>

    <Deep v-model="formData" />
    <button @click="onClick">click me</button>
    <div>parent: {{ formData }}</div>
  </q-page>
</template>

<script setup>
import { reactive } from 'vue';
import Deep from 'src/components/Deep.vue';
import { reass9 } from 'reass9';
import cloneDeep from 'lodash/cloneDeep';

const initFormData = { input1: '', input2: { hi: 'asd' } };
const formData = reactive(cloneDeep(initFormData));

const onClick = () => { reass9(formData, cloneDeep(initFormData)); };
</script>
