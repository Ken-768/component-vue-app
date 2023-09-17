<script>
  export default {
      inheritAttrs: false,
    };
</script>
<script setup>
  import {useAttrs} from 'vue';
  import { ref } from 'vue';
  const attrs = useAttrs();
  console.log(attrs);

  const props = defineProps({
    name: String,
  });
  const name = ref(props.name);
  const emit = defineEmits(['changeNameEvent']);

  const changeName = () => {
    emit('changeNameEvent', name.value);
  }
</script>

<template>
  <div>
    <h2 class="info">子コンポーネント</h2>
    <p :class="attrs.class" :style="attrs.style">class属性の渡し方確認中</p>
    <p>Hello {{ props.name }}</p>
    <input
      type="text"
      v-model="name"
      @input="changeName"
    />
  </div>
</template>
