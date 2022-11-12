<script setup>
import { defineProps, toRefs, computed } from 'vue';
import { formatDistance } from 'date-fns';

const props = defineProps({
  cover: {
    type: String,
    required: true
  },
  centerImage: {
    type: Boolean,
    default: false,
  },
});

const { cover, centerImage } = toRefs(props);

function reformatDate(date) {
  return formatDistance(new Date(date), new Date(), { addSuffix: true });
}
</script>

<template>
  <div class="bg-white p-10 rounded-xl w-1/3 my-4">
    <div :class="{ 'flex justify-center': centerImage }">
      <img :src="cover" alt="" width="90" />
    </div>
    <div>
      <slot></slot>
      <div class="border-t border-t-gray my-4">
        <slot name="footer" :reformatDate="reformatDate">
        </slot>
      </div>
    </div>
  </div>
</template>
