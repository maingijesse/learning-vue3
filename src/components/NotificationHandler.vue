<template>
    <div class="root relative">
        <button @click="isOpen = true" class="px-6 py-2 bg-teal-600 text-white">
            Open Modal
        </button>
        <teleport to="body">
            <div
                class="
                    modal
                    absolute
                    top-0
                    left-0
                    bg-black bg-opacity-25
                    w-full
                    h-screen
                    flex
                    justify-center
                    items-center
                "
                v-if="isOpen"
            >
                <ModalContent
                    :title="title"
                    :message="message"
                    @close="isOpen = false"
                />
            </div>
        </teleport>
    </div>
</template>

<script setup>
import { ref } from "vue";
import ModalContent from "./ModalContent.vue";

const isOpen = ref(false);
const title = ref("This is the modal title");
const message = ref(
    "This is the modal message passed down as prop to the child component"
);
</script>

<style>
</style>