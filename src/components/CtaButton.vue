<script setup>
defineProps(['label', 'dest']);
</script>

<template>
    <a :href="dest" class="py-2 bg-purple-600 hover:bg-purple-950 text-white font-bold rounded-full text-center">
        {{ label }}
    </a>
</template>

