<script setup>
import { h } from 'vue';

const props = defineProps({
  items: {
    type: Array,
    default: []
  }
})

const render = () => h('ul', {}, [
  props.items.map((item) => h('li', { class: 'text-gray-700'}, item))
])
</script>


<template>
  <render />
</template>
