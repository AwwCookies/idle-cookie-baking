<template>
  <h1>Idle Cookie Baking</h1>
  <p>Cookies baked: {{ count }}</p>
  <p>Money: {{ money }}</p>
  <button @click="count++">Bake Cookie</button>
</template>

<script setup>
import { ref } from "vue"
import { useLocalStorage, onKeyDown } from "@vueuse/core"

const count = useLocalStorage('count', 0)
const money = useLocalStorage('money', 0)

// debug
onKeyDown("d", () => {
  console.log('clearing local storage')
  localStorage.clear()
  location.reload(true)
})
</script>

<style>
body {
  display: flex;
  background-color: #2b2b2b;
  color:aliceblue;
}
#app {
  margin-left: auto;
  margin-right: auto;
}
</style>