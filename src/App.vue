<script setup>
import { ref, computed } from "vue"

const name = "Vue 3"
const counter = ref(0)
const favorites = ref([])

const increment = () => {
  counter.value++
}

const decrement = () => {
  counter.value--
}

const reset = () => {
  counter.value = 0
}

const add = () => {
  favorites.value.push(counter.value)
}

const blockAdd = computed(() => {
  const numSearch = favorites.value.find(num => num === counter.value)
  return numSearch || numSearch === 0;
})

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "zero"
  }
  return counter.value > 0 ? "positive" : "negative";
})
</script>

<template>
  <div class="container text-center mt-5">
    <h1>Hola {{ name }}!</h1>
    <h2 :class="classCounter">
      {{ counter }}
    </h2>
    <div class="btn-group">
      <button @click="increment" class="btn btn-success">Increment</button>
      <button @click="decrement" class="btn btn-danger">Decrement</button>
      <button @click="reset" class="btn btn-secondary">Reset</button>
      <button @click="add" :disabled="blockAdd" class="btn btn-primary">Add</button>
    </div>
    <h2 class="mt-3">Mis Favoritos</h2>
    <ul class="list-group mt-2">
      <li class="list-group-item" v-for="(item, index) in favorites" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<style>
.negative {
  color: red;
}

.positive {
  color: green;
}

.zero {
  color: black;
}
</style>