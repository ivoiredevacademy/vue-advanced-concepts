<script setup>
import { inject, computed, onMounted } from 'vue';
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  id: {
    type: Number,
    required: true,
  },
  active: {
    type: Boolean,
    default: false,
  }
})

const tabTitles = inject('tabTitles');
const activeTabId = inject('activeTabId');

onMounted(() => {
  tabTitles.value.push({ title: props.title, id: props.id });

  if(props.active) {
    activeTabId.value = props.id;
  }
});

const isActive = computed(() => activeTabId.value === props.id);

</script>

<template>
  <div v-if="isActive" class="py-4">
    <slot></slot>
  </div>
</template>
