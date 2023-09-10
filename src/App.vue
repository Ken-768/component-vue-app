<script setup>
import Hello from './components/Hello.vue';
import Child1 from './components/Child1.vue';
import Input from './components/Input.vue';
import Child2 from './components/Child2.vue';
import User from './components/User.vue';
import { ref } from 'vue';

const name = ref('John');
const changeName = () => {
  name.value = 'Jane';
}
//$emit
const handleEvent = (newName) => {
  name.value = newName;
}
const address = ref('');
</script>

<template>
  <h1>Vue 3 入門</h1>
  <Hello message="propsの使い方" :name="name" v-bind:price="1000" v-bind:is-admin="false" />
  <Child1 id="main" style="color:red" class="active" />
  <button @click="changeName">Change Name</button>
  <Child1 v-on:notification="handleEvent" />
  <Child1 @changeNameEvent="handleEvent" :name="name" />
  <p>name: {{ name }}</p>
  <p>address:{{ address }}</p>
  <input v-model="name" />
  <input v-model="address" />
  <!-- <Input :model-value="name" @update:model-value="name = $event" />
  <Input :model-value="address" @update:model-value="address = $event" /> -->
  <Child2 @changeNameEvent="handleEvent" :name="name" />
  <!-- slot -->
  <User>
    <!-- <template v-slot:title><h1>ユーザ情報</h1></template>
    <template v-slot:content>
      <div>
        <div>John Doe</div>
        <div>Jane Doe</div>
      </div>
    </template>
    <template v-slot:actions><button>ユーザ追加</button></template>
    <template v-slot:header="{message}">
      <div>{{ message }}</div>
    </template>
    <template v-slot:default="{message, content}">
      <div>{{ message }} / {{ content }}</div>
    </template> -->
    <template v-slot:default="{ user }">
      <li>{{ user.name }}</li>
    </template>
  </User>
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
