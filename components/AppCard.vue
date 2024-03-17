<script setup lang="ts">
defineProps<{
    title: string
    images?: string[]
    link: string
    description: string
    badges: string[]
    video?: string
    date: string
}>();

const colorsForBadge = {
    'Published': 'black',
    'Discarded': 'black',
    'Researching': 'black'
}
</script>

<template>
    <UCard>
        <UCarousel v-if="images" v-slot="{ item }" :items="images" class="mb-4 border rounded-md overflow-hidden shadow-sm" indicators :ui="{ item: 'basis-full' }">
            <img :src="item" class="object-cover" draggable="false">
        </UCarousel>
        <video v-else-if="video" :src="video" class="mb-4 rounded-md overflow-hidden border shadow-sm" autoplay muted playsinline></video>
        <div class="font-semibold text-lg mb-1">{{  title }}</div>
        <div class="text-neutral-500 text-sm mb-4">{{date}} • <a :href="link"><UIcon name="i-heroicons-link" class="mr-1"/>{{ link.replace('https://', '') }}</a></div>
        {{ description }}
        <div class="mt-4 flex gap-2">
            <UBadge v-for="b in badges" class="capitalize" :color="colorsForBadge[b] || 'gray'">{{ b }}</UBadge>
        </div>
    </UCard>
</template>