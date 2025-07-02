<script setup>
import { ref } from 'vue';
defineProps({
  user: String,
  age: Number,
});
let count = ref(0);

const increment = () => {
  count.value++;
};

const decrement = () => {
  count.value--;
};
</script>

<template>
  <div>Hello {{ user }}, {{ age }}</div>
  <button @click="decrement">-</button>
  count{{ count }}
  <button @click="increment">+</button>
</template>
<style scoped>
div {
  font-weight: bold;
}
</style>
