<script setup lang="ts">

const experiments = [[
    {
        title: 'Nuxt Editable',
        date: '2024',
        description: 'Nuxt Editable is a embeddable editor UI for Nuxt.js. It allows you to create collection schemas and connect them with your own database, and provide your clients with an easy to use UI to manage site content.',
        link: 'https://github.com/NvdB31/nuxt-editable/tree/main',
        images: ['https://github.com/NvdB31/nuxt-editable/raw/main/.github/assets/banner.svg'],
        badges: ['Built prototype', 'Open-source', 'Published'],
    },
    {
        title: 'Aanbiedingenradar',
        date: '2021',
        description: 'A free site that automatically scrapes the latest supermarket promotions from the major Dutch supermarkets. Built post-pandemic to alleviate the pain of increasing costs of living.',
        link: 'https://aanbiedingenradar.nl',
        images: [
            '/experiments/aanbiedingenradar-1.webp',
            '/experiments/aanbiedingenradar-2.webp',
        ],
        badges: ['Website', 'Free', 'Published']
    },
    {
        title: 'Sitestage',
        date: '2022',
        description: 'A chrome extension to create beautiful, interactive SaaS product demos in minutes. Discarded due to technical limitations with in-browser video rendering.',
        link: 'https://sitestage.app',
        badges: ['SaaS', 'Built prototype', 'Discarded'],
        video: '/experiments/sitestage.mp4'
    },
],
    [
    {
        title: 'Weeknight Recipes',
        date: '2024',
            description: 'An iOS app that suggests an AI-generated recipe for a simple weeknight dinner. With filterable options for cuisine, max prep. time and dietary restrictions. The recipe images are generated with Stable Diffusion.',
        images: ['/experiments/weeknight-recipes.webp'],
        link: 'https://weeknight.recipes',
        badges: ['Built prototype'],
    },
    {
        title: 'UI Pass',
        date: '2023',
        description: 'A productized service business that delivers complete, branded UI component kits for a fixed monthly fee. With subscriptions starting from €2999 per month.',
        link: 'https://ui-pass.com',
        images: ['/experiments/uipass.webp'],
        badges: ['Services', 'UX/UI']
    },
        {
            title: 'Preflight UI',
            date: '2022',
            description: 'An concept for a modular UI kit of components that could be flexibly adapted to many different styles, for them to work with any brand identity.',
            link: 'https://preflightui.com',
            images: ['/experiments/preflight-ui.webp', '/experiments/preflight-ui-2.webp'],
            badges: ['SaaS', 'UX/UI', 'Discarded']
        },
    ]
]

</script>


<template>
    <NuxtLayout :pattern="true">
        <AppSection>
            <AppPageHeading>🧪 Experiments</AppPageHeading>
            <article class="prose text-lg">
                <p>I love toying around with new ideas. I believe that the best way to find out the viability of an idea is to just... try it out! I often create a small prototype over the weekend – and use that to demonstrate and ask for feedback.</p>
                <p>The following is a collection of some of these ideas. Most of them never turn out to be commercially successful, but that's not the point! It's my personal outlet for creativity and a way for me to keep learning and stay up to date with things.</p>
            </article>
            <div class="grid sm:grid-cols-2 gap-8 mt-16 items-start">
                    <div class="flex flex-col gap-8">
                        <AppCard v-for="experiment in experiments[0]" v-bind="experiment"/>
                    </div>
                    <div class="flex flex-col gap-8">
                        <AppCard v-for="experiment in experiments[1]" v-bind="experiment"/>
                    </div>
                </div>
        </AppSection>
    </NuxtLayout>
</template>