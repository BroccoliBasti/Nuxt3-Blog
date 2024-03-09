<script setup lang="ts">
import { parseMarkdown } from '@nuxtjs/mdc/runtime';

const blabla = ref(``);
const wysiwyg = await computed(() => parseMarkdown(blabla.value));
</script>

<template>
    <h1 class="text-2xl font-bold mb-6">Post editor</h1>
    <div class="grid grid-cols-2 gap-9">
        <div>

            <textarea name="" id="blabla" cols="30" rows="10" v-model="blabla" placeholder="Write your post here"
                class="text-stone-900 bg-orange-100 p-2 outline-none focus-visible:outline-emerald-300">
            </textarea>
        </div>
        <MDC :value="wysiwyg" class="prose dark:prose-invert" />
    </div>
</template>
