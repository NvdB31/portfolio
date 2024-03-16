<template>
    <NuxtLayout>
        <AppSection>
            <AppPageHeading>Journey</AppPageHeading>
            <article>
                <ContentList path="/journey" v-slot="{ list }">
                    <ul class="flex flex-col-reverse">
                        <li v-for="(item, i) in list.sort((a, b) => a.year - b.year)" class="grid grid-cols-6">
                            <div class="font-bold text-xl mt-8">
                                <template v-if="list[i+1]?.year !== item.year">{{ item.year }}</template>
                            </div>
                            <div class="flex flex-col">
                                <div class="w-[1px] h-8 border-r ml-3" v-if="i !== list.length-1"></div>
                                <div class="rounded-full w-6 h-6 flex items-center justify-center bg-black" :class="{'mt-8': i === list.length-1}">
                                    <UIcon name="i-mdi-plus" color="white"/>
                                </div>
                                <div class="w-[1px] border-r flex-grow ml-3"></div>
                            </div>
                        <div class="col-span-4 py-8">
                            <h2 class="font-bold mb-2">{{ item.title }}</h2>
                            <div class="text-neutral-600">{{ item.description }}</div>
                            <img :src="item.image" v-if="item.image" class="mt-4 object-cover rounded-lg border"/>
                        </div>
                    </li>
                    </ul>
                </ContentList>
            </article>
        </AppSection>
    </NuxtLayout>
</template>