<template>
    <NuxtLayout>
        <section>
            <h1 class="text-4xl mb-4">
                Oops! <span class="text-rose-700 font-bold">{{ error.statusCode }}</span>
            </h1>

            <h2 class="text-xl text-zinc-500 dark:text-zinc-400">
                {{ error.statusMessage }}
            </h2>
        </section>
    </NuxtLayout>
</template>

<script setup>
defineProps({ error: Object });
useHead({
    title: 'Oops!'
});
</script>