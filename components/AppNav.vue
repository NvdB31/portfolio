<script setup lang="ts">
const router = useRouter()

defineShortcuts({
    '1': () => router.push('/'),
    '2': () => router.push('/stories'),
    '3': () => router.push('/journey'),
    '4': () => router.push('/experiments')
})

const navLinks = [
  [{
    label: 'Home',
    icon: 'i-heroicons-home',
      to: '/',
    badge: 1
  }, {
    label: 'Stories',
    icon: 'i-heroicons-book-open',
      to: `/stories`,
      badge: 2
  }, {
    label: 'Journey',
    icon: 'i-heroicons-rectangle-stack',
      to: '/journey',
    badge: 3
        },
    {
    label: 'Experiments',
    icon: 'i-heroicons-beaker-16-solid',
      to: '/experiments',
    badge: 4
  }]
]

const onlineLinks = [
    [{
        label: 'X (Twitter)',
        icon: 'i-ri-twitter-x-fill',
        to: 'https://twitter.com/nvdb31',
    }, {
        label: 'GitHub',
        icon: 'i-mdi-github',
        to: 'https://github.com/nvdb31'
        },
    {
        label: 'LinkedIn',
        icon: 'i-mdi-linkedin',
        to: 'https://www.linkedin.com/in/nick-van-den-berg-8b127964/'
        },
        {
            label: 'Instagram',
            icon: 'i-mdi-instagram',
        to: 'https://www.instagram.com/nick_vdb31'
        },
    {
            label: 'YouTube',
            icon: 'i-mdi-youtube',
        to: 'https://www.youtube.com/channel/UC00HclvQafwy9I44nMddThQ'
    }
]
]

const navigationUIProps = { base: 'transition-colors duration-500 before:transition-colors before:duration-500', icon: { base: 'transition-colors duration-500'}, active: 'before:bg-neutral-200', inactive: 'text-gray-700' }
</script>

<template>
    <aside class="flex-none sm:bg-neutral-50 flex sm:border-r flex-col">
        <div class="p-4">
            <NuxtLink to="/" class="p-2 flex gap-4 hover:bg-gray-100 rounded-md transition-colors duration-500">
                <UAvatar src="/avatar.webp" size="lg"/>
                <div>
                    <div class="font-semibold">Nick van den Berg</div>
                    <div class="text-neutral-500 text-sm">Senior software engineer</div>
                </div>
            </NuxtLink>
        </div>
            <UVerticalNavigation :links="navLinks" class="px-4" :ui="navigationUIProps"/>
            <UDivider class="my-6"/>
            <UVerticalNavigation :links="onlineLinks" class="px-4" :ui="navigationUIProps">
            <template #badge>
                <UIcon name="i-heroicons-arrow-top-right-on-square" class="ml-auto z-10"/>
            </template>
            </UVerticalNavigation>
            <div class="flex-grow"></div>
            <div class="p-6">
                <UButton size="lg" class="shadow" color="gray" to="/cv-n-van-den-berg.pdf" icon="i-heroicons-document-text" block target="_blank">Download Resume</UButton>
            </div>
    </aside>
    
</template>