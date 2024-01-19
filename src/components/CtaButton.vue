<script setup>
defineProps(['label']);
</script>

<template>
    <button class="bg-purple-600 hover:bg-purple-950 text-white font-bold py-2 rounded-full">
        {{ label }}
    </button>
</template>

