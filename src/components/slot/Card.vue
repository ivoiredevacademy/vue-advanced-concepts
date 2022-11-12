<script setup>
import { defineProps, toRefs } from 'vue';

const props = defineProps({
  post: {
    type: Object,
    required: true
  },
  centerImage: {
    type: Boolean,
    required: false,
    default: false,
  }
});

const { post, centerImage } = toRefs(props)
</script>

<template>
  <div class="bg-white p-10 rounded-xl w-1/3 ">
    <div :class="{ 'flex justify-center': centerImage }">
      <img :src="post.cover" alt="" width="90" />
    </div>
    <div>
      <span class="text-3xl font-semibold mb-2 flex">{{ post.title }}</span>
      <p class="text-gray-500">{{ post.description }}</p>
      <div class="flex justify-end">
        {{ post.createdAt.toString() }}
      </div>
    </div>
  </div>
</template>
