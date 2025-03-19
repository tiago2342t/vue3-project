<script setup>
import { ref } from 'vue'

let counter = ref(0)
const increment = () => {
  console.log('Aumentar contador')
  counter.value++
}
</script>

<template>
  <h2>{{ counter }}</h2>
  <button @click="increment">Aumentar</button>
</template>

<style>

</style>