<template>
    <section class="not-prose font-mono">
        <div class="column text-zinc-400 text-sm">
            <div>date</div>
            <div>title</div>
        </div>

        <ul>
            <li v-for="post in posts" :key="post._path">
                <NuxtLink :to="post._path" class="column hover:bg-pink-200 dark:hover:text-zinc-800">
                    <div :class="{
                        'text-transparent': !post.displayYear,
                        'text-zinc-400 dark:text-zinc-500': post.displayYear
                    }">
                        {{ post.year }} </div>
                    <div>{{ post.title }}</div>
                </NuxtLink>
            </li>
        </ul>
    </section>
</template>

<script setup>
const { data } = await useAsyncData(
    'blog-list',
    () => queryContent('/blog')
        .where({ _path: { $ne: '/blog' } })
        .only(['_path', 'title', 'publishedAt'])
        .sort({ publishedAt: -1 })
        .find()
);

const posts = computed(() => {
    if (!data.value) {
        return [];
    }

    const result = [];
    let lastYear = null;

    for (const post of data.value) {
        const year = new Date(post.publishedAt).getFullYear();
        const displayYear = year != lastYear;
        post.displayYear = displayYear;
        post.year = year;
        result.push(post);
        lastYear = year;
    }

    return data.value;
});
</script>

<style scoped>
.column {
    @apply flex items-center space-x-8 py-2 border-b border-zinc-200 dark:border-zinc-700;
}
</style>