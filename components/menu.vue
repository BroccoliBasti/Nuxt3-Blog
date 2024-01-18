<template>
    <nav class="font-mono">
        <ul class="flex space-x-4">
            <li>
                <NuxtLink to="/" class="link">Home</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/about" class="link">About</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/projects" class="link">Projects</NuxtLink>
            </li>
        </ul>
    </nav>
</template>

<style scoped>
.link {
    @apply p-1 hover:bg-emerald-200 hover:text-zinc-900 active:bg-emerald-200;
}
</style>