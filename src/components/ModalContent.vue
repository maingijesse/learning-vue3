<template>
   <onClickOutside @trigger='close'>
        <div class="bg-white p-12 rounded-lg">
        <h2>{{ title }}</h2>
        <p>{{ message }}</p>
        <button
            @click="$emit('close')"
            class="px-6 py-2 mt-4 bg-teal-600 text-white rounded-sm"
        >
            Close
        </button>
    </div>
   </onClickOutside>
</template>

<script setup>

import {onClickOutside} from '@vueuse/core'
const props = defineProps({
    title: String,
    message: String,
});

const emit = defineEmits(["close"]);

</script>

<style>
</style>