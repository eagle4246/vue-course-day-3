<script setup>
import Message from './auo/ui/Message.vue';
import { ref } from 'vue'

const total = ref(0)
const scores = {}
const handleCounterUpdate = (user, count) => {
  console.log('emit', user, count)
  scores[user] = count
  total.value = Object.values(scores).reduce((acc,cv)=> acc += cv)
}

</script>

<template>
  <h1>AUO Day 3 </h1>
  <h2> {{ total }}</h2>
  <Message user="Alice" @counterUpdate="handleCounterUpdate" />
  <Message user="Bob" @counterUpdate="handleCounterUpdate" />
</template>

<style scoped></style>
