<template>
    <nav class="font-mono">
        <ul class="flex flex-col md:flex-row md:space-x-4">
            <li>
                <NuxtLink to="/" class="link">Home</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/about" class="link">About</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/projects" class="link">Projects</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/blog" class="link">Blog</NuxtLink>
            </li>
        </ul>
    </nav>
</template>

<style scoped>
.link {
    @apply p-1 hover:bg-emerald-200 hover:text-zinc-900 text-2xl md:text-base;
}
</style>