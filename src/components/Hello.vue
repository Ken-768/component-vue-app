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
  //componentの基本

  const props = defineProps({
    message: {type: String, required: true},
    name: {type: String, default: 'Jane'},
    price: Number,
    isAdmin: Boolean,
  });

  // const props2 = defineProps({
  //   price: Number,
  // });
</script>

<template>
  <h2>Hello Component</h2>
  <p>Ref count: {{ count }}</p>
  <p>Reactive count: {{ state.count }}</p>
  <div>
    <button @click="addRefCount">RefCount+</button>
    <button @click="addReactiveCount">ReactiveCount+</button>
  </div>
  <!-- componentの基本 -->

  <p>{{ props.name }} {{ props.message }}</p>
  <p>{{ props.price + 100 }}</p>
  <p v-if="props.isAdmin">管理者です</p>
  <p v-else>管理者ではありません</p>
</template>
