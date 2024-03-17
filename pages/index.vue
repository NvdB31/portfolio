
<script setup lang="ts">
const ageInMilliseconds = new Date() - new Date('1994-04-13');
const ageInYears = Math.floor(ageInMilliseconds / (365.25 * 24 * 60 * 60 * 1000));
const currentAge = ageInYears;
</script>

<template>
    <NuxtLayout>
        <AppSection>
            <AppPageHeading>👋 Hi, I'm Nick</AppPageHeading>
            <article class="prose text-lg">
                <p>Nice to meet you here! I'm a {{ currentAge }}-year old freelance senior software engineer, based in Eindhoven.</p>
                <p>My current main client is <a class="underline" href="https://dpgmedia.nl">DPG Media</a>, the Netherlands' largest media publisher. Previously, I worked at Sendcloud. I also created <a href="https://handoff-site.webflow.io" target="_blank">Handoff</a>, a design tool, and owned a digital agency called Cloudrocket.</p>
                <div class="grid sm:grid-cols-2 mt-8">
                    <div class="">
                        <h2 class="text-xl mt-0 mb-1">Services</h2>
                        <ul class="mt-0">
                            <li>👨‍💻 Software development</li>
                            <li><UIcon name="i-devicon-vuejs"/> Vue / Nuxt.js consulting</li>
                            <li><UIcon name="i-devicon-react"/> React / Next.js consulting</li>
                            <li>📐 UI Design</li>
                        </ul>
                        <div class="flex gap-2">
                            <UButton color="black" size="lg" to="https://calendly.com/nickvandenberg31/intro" class="no-underline" target="_blank">Schedule a call</UButton>
                            <UButton color="gray" size="lg" to="mailto:nickvandenberg31@gmail.com?subject=Inquiry software engineering" class="no-underline">Contact me</UButton>
                        </div>
                    </div>
                </div>
            </article>
        </AppSection>
    </NuxtLayout>
</template>

