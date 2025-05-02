<template>
    <div class="w-full flex items-center justify-center gap-2 h-screen text-white">
        <div class="w-1/2 flex items-center justify-center">
            <h1 class="text-2xl font-semibold">This is My Test Function</h1>
        </div>
        <div class="w-1/2 flex flex-col items-start justify-center px-4">
            <NuxtLink to="/click_copy" class="p-2 rounded-md">Click Copy</NuxtLink>
        </div>
    </div>
</template>

<script setup>
useHead({
    title: "Home",
})
</script>
