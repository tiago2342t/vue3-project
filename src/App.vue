<script setup>
const name = 'Vue dynamic'
const styleColor = "color: blue"
const arrayColors = ['blue', 'red', 'yellow']
const activo = false
</script>

<template>
  <h1>Hello {{ name.toUpperCase() }}!</h1>
  <h2>{{ arrayColors }}</h2>
  <h2 :style="`color: ${arrayColors[0]}`">Texto colorido</h2>
  <h2>
    {{ activo ? 'Estoy activo' : 'Estoy inactivo' }}
  </h2>
</template>

<style>
h1 {
  color: red;
}
</style>