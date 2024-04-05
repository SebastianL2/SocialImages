<template>
    <label v-bind="$attrs" class="label" :class="entering ? 'bg-gray-500' : 'bg-gray-100'" @drop.prevent="handleDrop" @dragenter="entering=true" @dragleave="entering=false">
        <input multiple type="file" class="input" @input="handleInput">
        <span class="message"> -> Drop your files here</span>
    </label>
</template>

<script setup lang="ts">
import { onMounted, onUnmounted, ref, defineEmits } from 'vue';
import { UpdateIcon } from '@radix-ui/react-icons';
const events = ["dragenter", "dragleave", "dragover"];

const entering = ref(false);

const emit = defineEmits(["upload"]);

function handleDrop(e) {
    e.preventDefault();
    const files = e.dataTransfer?.files;
    if (files) {
        emit("upload", Array.from(files));
    }
}

function handleInput(e) {
    const files = e.target.files;
    if (files) {
        emit("upload", Array.from(files));
    }
}

onMounted(() => {
    events.forEach(event => document.body.addEventListener(event, (e)=>e.preventDefault()));
});

onUnmounted(() => {
    events.forEach(event => document.body.removeEventListener(event, (e)=>e.preventDefault()));
});
</script>

<style scoped>
.label {
    @apply relative transition-all ease-in-out duration-300 border border-gray-500 hover:bg-gray-400;
}
.input {
    @apply absolute top-0 left-0 w-full h-full hidden;
}
.message {
    @apply absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2; 
}
</style>
