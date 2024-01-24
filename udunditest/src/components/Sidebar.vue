<script setup lang="ts">
import { defineProps } from 'vue';

const props = defineProps({
  formOpen: Boolean
});
</script>

<template>
    <div class="sidebar max-w-[410px] w-full h-screen flex z-[1] justify-end items-end relative" :class="{'open': formOpen}">
        <div class="panel h-screen w-[120px] transition-all duration-1000 absolute left-[-120px]" :class="{'left-0': formOpen}"></div>
        <div class="wrap">
            <slot name="info"></slot>
            <slot name="menuSection"></slot>
            <slot name="buttonWrapper"></slot>
        </div>
    </div>
</template>

<style scoped>
.sidebar {
  background: #611818;
  transition: 1s;
}

.panel {
  background: #3b1010;
}
</style>