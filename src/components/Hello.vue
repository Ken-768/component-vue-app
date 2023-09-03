<script setup>
  import {ref, reactive} from 'vue';

  const count = ref(0);
  const state = reactive({
    count: 1,
  });

  const addRefCount = () => {
    count.value++;
  };

  const addReactiveCount = () => {
    state.count++;
  }
</script>

<template>
  <h2>初めてのコンポーネント</h2>
  <p>Ref count: {{ count }}</p>
  <p>Reactive count: {{ state.count }}</p>
  <div>
    <button @click="addRefCount">RefCount+</button>
    <button @click="addReactiveCount">ReactiveCount+</button>
  </div>
</template>
