<template>
    <div class="min-h-screen bg-slate-900">
        <AppHeader />
        <div class="min-h-screen">
            <slot />
        </div>
        <AppFooter />
    </div>
</template>

<script lang="ts" setup>
import "swiper/css";
</script>



