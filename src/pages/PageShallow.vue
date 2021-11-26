<template>
  <q-page padding>
    <h1>Page Shallow</h1>

    <Shallow v-model="formData" />
    <button @click="onClick">click me</button>
    <div>parent: {{ formData }}</div>
  </q-page>
</template>

<script setup>
import { reactive } from 'vue';
import { reass9 } from 'reass9';
import Shallow from 'src/components/Shallow.vue';

const formData = reactive({ input1: 'hello', input2: '' });

const onClick = () => { reass9(formData, {}); };

</script>
