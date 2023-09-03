<script setup>
import Hello from './components/Hello.vue';
import Child from './components/Child.vue';
import { ref } from 'vue';

const name = ref('John');
const changeName = () => {
  name.value = 'Jane';
}
</script>

<template>
  <h1>Vue 3 入門</h1>
  <Hello message="propsの使い方" :name="name" v-bind:price="1000" v-bind:is-admin="false" />
  <Child id="main" style="color:red" class="active" />
  <button @click="changeName">Change Name</button>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
