<script setup lang="ts">
const route = useRoute();
</script>

<template>
    <div v-if="route.path.includes('stories')" class="sm:border-r min-h-screen bg-white">
            <div class="p-4 border-b">
                <h2 class="font-semibold">Stories</h2>
            </div>
            <ul class="p-4">
                <ContentNavigation :query="queryContent('stories')" v-slot="{ navigation }">
                <li v-for="article in navigation[0].children" class="p-2 px-3 rounded-md hover:bg-neutral-200 transition-colors duration-500 dark:hover:bg-neutral-800">
                    <NuxtLink :to="article._path">
                        <h3 class="font-medium">{{ article.title }}</h3>
                        <div class="text-neutral-500 text-sm">{{  article.date }} • {{ article.category }}</div>
                    </NuxtLink>
                </li>
                </ContentNavigation>
            </ul>
        </div>
</template>