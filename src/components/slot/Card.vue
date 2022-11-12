<script setup>
import { defineProps, toRefs, computed } from 'vue';
import { formatDistance } from 'date-fns';

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
console.log(props.post.createdAt);
console.log(new Date(props.post.createdAt));
const { post, centerImage } = toRefs(props)
const formattedCreatedAt = computed(() => formatDistance(new Date(props.post.createdAt), new Date(), { addSuffix: true }))
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
        {{ formattedCreatedAt }}
      </div>
    </div>
  </div>
</template>
