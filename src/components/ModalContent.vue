<template>
    <div class="bg-white p-12 rounded-lg" ref="modalContent">
        <h2>{{ title }}</h2>
        <p>{{ message }}</p>
        <button
            @click="$emit('close')"
            class="px-6 py-2 mt-4 bg-teal-600 text-white rounded-sm"
        >
            Close
        </button>
    </div>
</template>

<script setup>
import {ref} from 'vue'
import {onClickOutside} from '@vueuse/core'
const props = defineProps({
    title: String,
    message: String,
});

const emit = defineEmits(["close"]);

const modalContent = ref(null)

onClickOutside((modalContent), (event) => {
    emit('close')
})
</script>

<style>
</style>