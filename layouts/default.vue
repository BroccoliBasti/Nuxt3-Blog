<template>
    <div class="container mx-auto max-w-2xl selection:bg-sky-200 selection:text-zinc-900">
        <header class="flex justify-between items-center mt-5">
            <div class="flex items-center space-x-12">

                <div class="hidden md:block">
                    <NuxtLink to="/"
                        class="text-xl font-semibold p-2 text-amber-600 dark:text-amber-400 dark:hover:bg-zinc-800">ⵘ Basti
                    </NuxtLink>
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
    @apply border-rose-200 text-zinc-100 hover:bg-rose-200 dark:hover:text-zinc-900 dark:hover:border-rose-200;
}
</style>