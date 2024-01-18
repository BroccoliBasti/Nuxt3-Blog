<template>
    <div class="container mx-auto max-w-2xl">
        <header class="flex justify-between items-center mt-5">
            <div>
                <NuxtLink to="/" class="text-xl font-semibold p-2 text-amber-400">♥ Basti</NuxtLink>
            </div>
            <Menu />
        </header>
        <main class="p-2 mt-10">
            <slot />
        </main>
    </div>
</template>

<script setup>
const colorMode = useColorMode();
console.log(colorMode.preference);

useHead({
    titleTemplate: '%s - Basti'
});
</script>

<style>
body {
    @apply bg-amber-50 text-zinc-700 dark:bg-zinc-900 dark:text-amber-50;
}

.repo {
    @apply hover:bg-amber-100 dark:hover:text-zinc-900 dark:hover:border-amber-100;
}
</style>