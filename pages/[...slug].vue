<template>
    <NuxtLayout>
        <div class="flex w-full">
            <AppStoriesNav class="hidden sm:block"/>
            <div class="flex-grow">
                <AppSection>
                <UContainer :ui="{ constrained: 'max-w-fit'}">
                        <UButton icon="i-heroicons-arrow-left-20-solid" to="/stories" class="mb-4 rounded-full sm:hidden" color="gray"></UButton>
                        <ContentDoc class="prose" />
                    </UContainer>
                </AppSection>
            </div>
        </div>
    </NuxtLayout>
</template>