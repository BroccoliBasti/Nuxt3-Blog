<template>
    <div>
        This page is about me.
    </div>
    <div>
        <button @click="enableCustomLayout">Update layout</button>
    </div>
</template>

<script setup>
// definePageMeta({
//     layout: "another"
// });
function enableCustomLayout() {
    setPageLayout('another');
}
</script>