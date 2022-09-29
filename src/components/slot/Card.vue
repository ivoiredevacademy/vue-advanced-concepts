<script setup>
import { defineProps, toRefs } from 'vue';

const props = defineProps({
    post: {
        type: Object,
        required: true
    }
});

const { post } = toRefs(props)
</script>

<template>
    <div class="bg-white p-10 rounded-xl w-1/3">
        <div >
            <img :src="post.cover" alt="" width="100"/>
        </div>
        <div >
            <span class="text-3xl font-semibold mb-2 flex">{{ post.title }}</span>
            <p class="text-gray-500">{{ post.description }}</p>
        </div>
        <div class="flex justify-end">
            {{ post.createdAt.toString() }}
        </div>
    </div>
</template>