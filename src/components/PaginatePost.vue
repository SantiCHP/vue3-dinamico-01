<script setup>
defineProps(['inicio', 'fin', 'maxLength']);

const emit = defineEmits(['next', 'prev']);

</script>

<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button @click="emit('prev')" type="button" class="btn btn-outline-primary" :disabled="inicio === 0">
            Previous
        </button>
        <div class="d-flex  align-items-center align-content-center bg-light">
            <span class="text-muted mx-2 align-middle">{{ inicio }} - {{ fin }} de {{ maxLength }}</span>
        </div>
        <button @click="emit('next')" type="button" class="btn btn-outline-primary" :disabled="fin === maxLength">
            Next
        </button>
    </div>
</template>