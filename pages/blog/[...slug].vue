<template>
    <article
        class="prose dark:prose-invert prose-pre:bg-emerald-200 dark:prose-pre:bg-cyan-900/25 prose-pre:text-zinc-700 dark:prose-pre:text-amber-50 max-w-none">
        <ContentDoc>
            <template #not-found>
                <h1>404 - Document not found</h1>
                <P>This blog post could not be found.</P>
            </template>
            <template v-slot="{ doc }">
                <div class="grid grid-cols-6 gap-16">
                    <div :class="{ 'col-span-6 md:col-span-4': doc.toc, 'col-span-6': !doc.toc }">
                        <ContentRenderer :value="doc" />
                    </div>
                    <div class="hidden md:col-span-2 md:block not-prose" v-if="doc.toc">
                        <aside class="sticky top-8">
                            <div class="font-semibold mb-2 text-amber-50">
                                Table of Contents
                            </div>
                            <nav>
                                <TocLinks :links="doc.body.toc.links" :active-id="activeId" />
                            </nav>
                        </aside>
                    </div>
                </div>
            </template>
        </ContentDoc>
    </article>
</template>

<script setup>
const activeId = ref(null);

onMounted(() => {

    let elements = []; // Used in both setTimeout() and onBeforeUnmount() so it is declared here.

    const callback = (entries) => {
        for (const entry of entries) {
            if (entry.isIntersecting) {
                activeId.value = entry.target.id;
                break;
            }
        }
    };

    const observer = new IntersectionObserver(callback, {
        root: null,
        threshold: 0.5
    });

    setTimeout(() => {
        const elements = document.querySelectorAll('h2, h3');

        for (const element of elements) {
            observer.observe(element);
        }
    }, 150);

    onBeforeUnmount(() => {
        for (const element of elements) {
            observer.unobserve(element);
        }
    }); // Can not be run after a timeout so it has to be outside of setTimout()
});
</script>