<script setup>
import { ref } from 'vue';

const props = defineProps({
  user: String,
});

const emit = defineEmits(['counterUpdate'])
let counter = ref(0);

const increment = () => {
  counter.value++;
  emit('counterUpdate', props.user, counter.value)
};

const decrement = () => {
  counter.value--;
  emit('counterUpdate', props.user, counter.value)
};
</script>

<template>
  <div>Hello {{ user }}</div>
  <button @click="decrement">-</button>
  {{ counter }}
  <button @click="increment">+</button>
</template>
<style scoped>
div {
  font-weight: bold;
}
</style>
