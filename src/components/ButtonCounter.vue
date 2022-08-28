<script setup>
import { ref } from "vue";

const counter = ref(0);
const increment = () => counter.value++;
</script>

<template>
    <button @click="increment" class="btn btn-secondary mx-2">Counter {{ counter }}</button>
</template>

