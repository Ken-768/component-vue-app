<script setup>
import { inject } from 'vue';
import { counter } from '../store/countStore';

const { message } = defineProps(['message']);
const message2 = inject('message');

const count = inject('count');
const addCount = inject('addCount');
</script>

<template>
  <h3>CompBコンポーネント</h3>
  <p>{{ message }}</p>
  <p>{{ message2 }}</p>
  <p>Count:{{ counter.count }}</p>
  <button @click="counter.addCount">+</button>
</template>
