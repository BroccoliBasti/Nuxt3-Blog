<template>
    <div class="container mx-auto max-w-2xl">
        <header class="flex justify-between items-center mt-5">
            <div class="flex items-center space-x-12">

                <div>
                    <NuxtLink to="/" class="text-xl font-semibold p-2 text-amber-600 dark:text-amber-400">ⵘ Basti</NuxtLink>
                </div>

                <Menu />
            </div>

            <ClientOnly>
                <ColorModeSelector />
            </ClientOnly>
        </header>
        <main class="p-2 mt-10">
            <slot />
        </main>
    </div>
</template>

<script setup>
useHead({
    titleTemplate: '%s - Basti'
});
</script>

<style>
body {
    @apply bg-amber-50 dark:bg-zinc-900 text-zinc-700 dark:text-amber-50;
}

.repo {
    @apply border-pink-200 hover:bg-pink-200 dark:hover:text-zinc-900 dark:hover:border-pink-200;
}
</style>