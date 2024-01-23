<template>
    <article
        class="prose dark:prose-invert prose-pre:bg-white dark:prose-pre:bg-zinc-800 prose-pre:text-zinc-700 dark:prose-pre:text-zinc-300">
        <ContentDoc />
    </article>
</template>

<script setup>
const route = useRoute();
console.log(route.path);
</script>