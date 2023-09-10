<script setup>
  import { ref } from 'vue';

  const users = ref([]);

  const fetchPost = async () => {
    const res = await fetch('https://jsonplaceholder.typicode.com/users');
    users.value = await res.json();
  };
  fetchPost();
</script>
<template>
  <!-- <div>
    <slot name="title"></slot>
  </div>
  <div>
    <slot name="content"></slot>
  </div>
  <div>
    <slot name="actions"></slot>
  </div>
  <slot name="header" message="ヘッダー"></slot>
  <slot message="ユーザ" content="コンテント"></slot> -->
  <slot v-for="user in users" :user="user"></slot>
</template>
