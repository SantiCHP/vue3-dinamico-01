<script setup>

// defineProps(['title', 'id', 'body']);

// String, Number, Boolean, Array, Object, Date, Function, Symbol
defineProps({
    title: String,
    id: Number,
    body: {
        type: String,
        default: 'Sin descripción'
    },
    cambiarFavorito: Function
});

// const emit = defineEmits(['cambiarFavoritoNombre']);

// emit(['cambiarFavoritoNombre', title)
</script>

<template>
    <div class="card mt-2">
        <div class="card-body">
            <h5 class="card-title">{{ id }} - {{ title }}</h5>
            <p>{{body}}</p>
            <button 
                class="btn btn-outline-primary" 
                @click="cambiarFavorito(title)" 
                
            >
                ❤️
            </button>
        </div>
    </div>
</template>