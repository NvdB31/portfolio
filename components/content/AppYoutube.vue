<script setup lang="ts">
defineProps<{ embedUrl: string; }>();
</script>

<template>
    <iframe class="w-full aspect-[16/9] shadow-md rounded-lg" :src="embedUrl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</template>