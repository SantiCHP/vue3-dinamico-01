<script setup>
import { ref, computed } from "vue";
const name = "Vue 3 dinámico";

const counter = ref(0);
const arrayCounter = ref([]);

const increment = () => counter.value++;
const decrement = () => counter.value--;
const reset = () => (counter.value = 0);
const add = () => arrayCounter.value.push(counter.value);

const blockNumber = computed(() => {
  const number = arrayCounter.value.find((num) => num === counter.value);
  return number || number === 0;
})

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "text-dark";
  }

  return counter.value > 0 ? "text-success" : "text-danger";
});

</script>

<template>
  <div class="container d-flex justify-content-center mt-3">
    <h1 class="text-danger">Hey! {{ name.toUpperCase() }}</h1><br>
    <h2 :class="classCounter">{{ counter }}</h2>
    <div class="btn-group mt-4">
      <button class="btn btn-primary mx-2" @click="increment">Aumentar</button>
      <button class="btn btn-warning mx-2" @click="decrement">Disminuir</button>
      <button class="btn btn-danger mx-2" @click="reset">Resetear</button>
      <button class="btn btn-info mx-2" @click="add" :disabled="blockNumber">Añadir</button>
    </div>
    <div class="d-flex justify-content-center">
      <ul class="list-group fs-2 mt-4">
        <li
          class="list-group-item"
          v-for="(number, index) in arrayCounter"
          :key="index"
        >
          {{ number }}
        </li>
      </ul>
    </div>

  </div>
</template>

<style></style>