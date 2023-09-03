<script>
  export default {
      inheritAttrs: false,
    };
</script>
<script setup>
  import {useAttrs} from 'vue';
  const attrs = useAttrs();
  console.log(attrs);
</script>

<template>
  <div>
    <h2 class="info">子コンポーネント</h2>
    <p :class="attrs.class" :style="attrs.style">class属性の渡し方確認中</p>
  </div>
</template>
