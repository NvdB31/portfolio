<script setup lang="ts">
const route = useRoute()
const isStoriesPage = computed(() => route.path.includes('stories'))
const isStoriesFrontPage = computed(() => route.path === '/stories')
const layoutCustomProps = useAttrs()

const isMobileMenuOpen = ref(false)

const modalUI = {
    container: '!p-0', overlay: { background: 'bg-black/50' }, transition: {
        enter: 'ease-out duration-[400ms]',
        enterFrom: 'opacity-100 translate-y-32 sm:translate-y-0',
        enterTo: 'opacity-100 translate-y-0',
        leaveFrom: 'opacity-100 translate-y-0 sm:scale-100',
        leaveTo: 'opacity-100 translate-y-full sm:translate-y-0',
        leave: 'ease-out duration-[400ms]',
} }
</script>

<template>
    <div class="transition-colors" :class="{'bg-black': isMobileMenuOpen }">
        <div class="sm:flex min-h-full pt-14 sm:pt-0 relative transition-transform origin-top duration-[400ms] bg-white" :class="{'scale-[0.93] translate-y-4 rounded-t-lg': isMobileMenuOpen}">
            <header class="py-3 px-4 border-b flex items-center font-semibold text-sm gap-2 sm:hidden absolute top-0 left-0 right-0 bg-white z-10 justify-between" :class="{'rounded-t-lg': isMobileMenuOpen}">
                <button @click="isMobileMenuOpen = true" class="w-8 h-8">
                    <UAvatar src="/avatar.webp"/>
                </button>
                <UButton to="/cv-n-van-den-berg.pdf" size="xs" color="gray" icon="i-heroicons-document-text" target="_blank"> Resume</UButton>
            </header>
            <UModal v-model="isMobileMenuOpen" :ui="modalUI">
                <AppNav/>
            </UModal>
            <AppNav class="hidden sm:fixed sm:flex h-screen w-72"/>
            <main class="flex-grow sm:pl-72 min-h-screen" :class="{ 'pattern-bg': layoutCustomProps.pattern  }">
                <template v-if="isStoriesPage">
                    <slot/>
                </template>
                <UContainer :ui="{ constrained: 'max-w-4xl'}" v-else>
                    <slot/>
                </UContainer>
            </main>
        </div>
    </div>
</template>

<style scoped>

.pattern-bg {
    background-color: #ffffff;
background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23000000' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}

</style>