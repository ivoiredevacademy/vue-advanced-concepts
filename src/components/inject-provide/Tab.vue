<script setup>
import { inject } from 'vue';
const props = defineProps({
  title: {
    type: String,
    required: true,
  }
})

const tabsTitle = inject('tabsTitle');
console.log(tabsTitle);
</script>

<template>
  <div>

    <slot></slot>
  </div>
</template>
