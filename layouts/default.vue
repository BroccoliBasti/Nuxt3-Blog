<template>
    <div class="container mx-auto max-w-2xl">
        <header class="flex justify-between items-center mt-5">
            <div>
                <NuxtLink to="/" class="text-xl font-semibold p-2 text-red-300">Basti</NuxtLink>
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
    @apply bg-white text-gray-700 dark:bg-gray-900 dark:text-gray-300;
}

li>a {
    @apply dark:hover:text-gray-900;
}
</style>